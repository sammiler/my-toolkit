<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# 🛡️ Infrastructure & Security: A Deep Dive

This document provides a detailed breakdown of the philosophy, tools, and workflow behind my citadel's foundational layer, which was summarized on the main `README.md`.

### The Philosophy: Zero Trust, Total Observability & Automated Maintenance

The security and stability of the entire citadel rest on this foundation. My approach is governed by three core principles:

1.  **Zero Trust Access**: No service is ever directly exposed to the public internet. Every request must pass through a single, authenticated, and encrypted gateway.
2.  **Total Observability**: I can't protect what I can't see. This means having a multi-faceted view of the citadel's health: from external reachability to internal performance metrics.
3.  **Automated Maintenance**: The citadel should be self-maintaining where possible. Security patches and updates should be applied automatically to minimize the window of vulnerability.

---

### The Tools in Detail

#### 🚪 Gateway: [Cloudflare Tunnels](https://www.cloudflare.com/products/tunnel/)

*   **Why Cloudflare Tunnels?**: It perfectly embodies the Zero Trust principle. It creates a secure, outbound-only connection from my VPS to the Cloudflare network. My server's IP address and open ports are completely hidden, eliminating a massive attack surface.

#### 🚦 Dispatcher: [Pangolin](https://github.com/fosrl/pangolin)

*   **Why Pangolin?**: It serves as the citadel's internal traffic director. While Cloudflare Tunnels securely brings traffic *to* my server, Pangolin takes over from there. It's an enhanced Nginx reverse proxy with a simple web UI. It routes incoming requests to the correct Docker container based on the hostname, manages internal SSL, and simplifies what would otherwise be complex Nginx configuration files.

#### 🔑 Vault: [Vaultwarden](https://github.com/dani-garcia/vaultwarden)

*   **Why Vaultwarden?**: A lightweight, open-source implementation of the Bitwarden API. It provides all the core features of a modern password manager. As the master key to my digital life, self-hosting is non-negotiable.

#### 🔭 Sentinel: [Uptime Kuma](https://github.com/louislam/uptime-kuma)

*   **Why Uptime Kuma?**: It provides the "external view" of my services. It's my vigilant guard, watching over every exposed service to ensure it's responsive. Its rich notification system ensures I'm the first to know if anything goes down.

#### 🩺 Physician: [Prometheus + Grafana + Node Exporter](https://www.netdata.cloud/)

*   **Why Prometheus + Grafana + Node Exporter?**: It provides the critical "metrics pipeline." While Uptime Kuma tells me if a service is down, Prometheus tells me how the system is behaving over time. Node Exporter exposes host-level metrics (CPU, memory, disk, network), Prometheus scrapes and stores them as time series, and Grafana visualizes them with flexible dashboards. This stack is invaluable for both real-time monitoring and historical analysis, making it possible to spot performance trends, debug resource bottlenecks, and plan capacity ahead.

#### ⚙️ Quartermaster: [Watchtower](https://containrrr.dev/watchtower/)

*   **Why Watchtower?**: This tool embodies the "Automated Maintenance" principle. It runs in the background and constantly monitors my running Docker containers. When it detects that a new version of an image has been pushed to the registry, it automatically pulls the new image and gracefully restarts the container. This ensures I am always running the latest, most secure versions of my services with zero manual intervention.

#### 🚢 Helm: [Portainer](https://www.portainer.io/)

*   **Why Portainer?**: This is the command deck. Portainer's web UI provides an exceptional "management view" of my entire Docker environment. It simplifies complex tasks like deploying stacks, managing volumes, and inspecting container logs, making it an indispensable tool for day-to-day operations.
<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# 🛡️ Infrastructure & Security: A Deep Dive

This document provides a detailed breakdown of the philosophy, tools, and workflow behind my citadel's foundational layer, which was summarized on the main `README.md`.

### The Philosophy: Zero Trust & Total Observability

The security and stability of the entire citadel rest on this foundation. My approach is governed by two core principles:

1.  **Zero Trust Access**: No service is ever directly exposed to the public internet. Every request, without exception, must pass through a single, authenticated, and encrypted gateway. The internal network is treated as hostile by default.
2.  **Total Observability**: I can't protect what I can't see. This means having a multi-faceted view of the citadel's health:
    *   **External View (Uptime)**: Is the service reachable from the outside world?
    *   **Internal View (Performance)**: How is the service and the underlying system performing? Are there any resource bottlenecks or anomalies?
    *   **Management View (Control)**: Can I easily manage the lifecycle of all services?

---

### The Tools in Detail

#### 🚪 Gateway: [Cloudflare Tunnels](https://www.cloudflare.com/products/tunnel/)

*   **Why Cloudflare Tunnels?**: It perfectly embodies the Zero Trust principle. It creates a secure, outbound-only connection from my VPS to the Cloudflare network. My server's IP address and open ports are completely hidden from the internet, eliminating a massive attack surface. It also provides world-class DDoS protection and a global CDN for free.

#### 🔑 Vault: [Vaultwarden](https://github.com/dani-garcia/vaultwarden)

*   **Why Vaultwarden?**: It's a lightweight, open-source implementation of the Bitwarden API, written in Rust. It provides all the core features I need—secure password storage, generation, and cross-device sync—without the resource overhead of the official self-hosted server. It's the master key to my entire digital life, so self-hosting it is non-negotiable.

#### 🔭 Watchtower: [Uptime Kuma](https://github.com/louislam/uptime-kuma)

*   **Why Uptime Kuma?**: It provides the "external view" of my services. It's incredibly easy to set up and has a beautiful, intuitive UI. It can monitor not just HTTP(s) endpoints but also specific ports, and even check for keywords on a page. Its rich notification system ensures I'm the first to know if any part of the citadel's perimeter is breached or unresponsive.

#### 🩺 Physician: [Netdata](https://www.netdata.cloud/)

*   **Why Netdata?**: It provides the critical "internal view." While Uptime Kuma tells me *if* a service is down, Netdata tells me *why* it might be struggling. It auto-discovers and monitors everything in real-time—from the host OS's CPU and memory to the resource usage of individual Docker containers. Its high-resolution, per-second metrics are invaluable for troubleshooting performance issues. For a single-node setup, its simplicity and power far outweigh the complexity of a Prometheus/Grafana stack.

#### 🚢 Helm: [Portainer](https://www.portainer.io/)

*   **Why Portainer?**: This is the command deck. While I am comfortable with the command line, Portainer's web UI provides an exceptional "management view" of my entire Docker environment. It simplifies complex tasks like deploying stacks, managing volumes and networks, and inspecting container logs. It's an indispensable tool for day-to-day operations and management.
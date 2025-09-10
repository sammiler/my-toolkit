<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# Deep Dive: Infrastructure & Security

My infrastructure philosophy is built on three pillars: **Stability, Simplicity, and Security**. This layer is the foundation for all other services, so every choice prioritizes long-term reliability and minimal maintenance overhead.

---

### 🚪 Gateway: Nginx Proxy Manager (NPM)

**Why I chose it**: Among contenders like Traefik and Caddy, I chose NPM because it strikes the perfect balance for a personal self-hosting setup. It combines the power of Nginx reverse proxying with the simplicity of Let's Encrypt's automated SSL certificate management, all through an incredibly intuitive web interface. This significantly reduces the cognitive load of configuration.

**Core Advantages**:
*   **GUI-Based Management**: There's no need to manually edit complex Nginx configuration files. Adding a new subdomain-based service is a point-and-click process.
*   **Automated SSL**: It has full, built-in support for Let's Encrypt, allowing for automatic acquisition and renewal of SSL certificates, with HTTPS enforced by default.
*   **Access Control Lists (ACLs)**: It provides an easy way to add a layer of HTTP Basic Authentication to any service, offering an extra blanket of security for internal or sensitive applications.

**Alternatives Considered**:
*   `Traefik`/`Caddy`: These are more powerful, especially with their automated service discovery via Docker labels. However, their configuration (whether through labels or files) presents a steeper learning curve. For a personal VPS with a relatively static set of services, the simplicity of NPM is a clear winner.

---

### 🔑 Vault: Vaultwarden

**Why I chose it**: A password manager is non-negotiable in a self-hosted environment. Vaultwarden is an unofficial Bitwarden API implementation written in Rust. It delivers 99% of the core functionality of the official server but with **exceptionally low resource consumption**.

**Core Advantages**:
*   **Extremely Lightweight**: Compared to the official .NET-based server, Vaultwarden's memory and CPU footprint is almost negligible, making it perfect for resource-constrained VPS environments.
*   **Full Compatibility**: It works flawlessly with all official Bitwarden clients (browser extensions, desktop apps, and mobile apps), ensuring a seamless user experience.
*   **Data Sovereignty**: All my passwords are end-to-end encrypted and stored exclusively on my own server, completely severing my dependency on third-party password management services.

---

### 🔭 Watchtower: Uptime Kuma

**Why I chose it**: A running system must be an observable system. Uptime Kuma stands out with its **beautiful, intuitive interface** and **deceptively simple configuration**.

**Core Advantages**:
*   **Effortless Setup**: Adding a new monitor (HTTP, Ping, Port, etc.) is straightforward and done entirely through the UI.
*   **Rich Notification Channels**: It supports dozens of notification methods (Telegram, Discord, Email, and more), ensuring I am the first to know if a service becomes unavailable.
*   **Aesthetic Status Pages**: It allows for the creation of public or private status pages that beautifully visualize the health of all my services—a very satisfying feature.
---

### 🚢 Helm: Portainer

**Why I chose it**: While the command line is powerful, a robust graphical interface is invaluable for day-to-day management, quick troubleshooting, and getting a clear overview of the environment. Portainer is the de facto standard for Docker Web UIs, offering comprehensive control over every aspect of the container ecosystem.

**Core Advantages**:
*   **Full Environment Management**: It provides a single pane of glass to manage containers, images, volumes, networks, and, most importantly, stacks (docker-compose files).
*   **Simplified Operations**: Actions like pulling an image, restarting a container, checking logs, or accessing a container's console become simple clicks in a web browser, which is far more efficient for quick tasks than SSHing and typing commands.
*   **Stack Management**: Its ability to deploy, edit, and manage `docker-compose.yml` files directly from the UI is a killer feature, streamlining the entire application lifecycle management process.
*   **Resource Monitoring**: Built-in, real-time stats for each container help me instantly identify which services are consuming the most CPU or memory.
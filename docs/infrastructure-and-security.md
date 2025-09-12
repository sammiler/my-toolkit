<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# Deep Dive: Infrastructure & Security

My infrastructure philosophy is built on three pillars: **Stability, Simplicity, and Security**. This layer is the foundation for all other services, so every choice prioritizes long-term reliability and minimal maintenance overhead.

---

### 🚪 Gateway: Cloudflare Tunnels

**Why I chose it**: For a truly private digital citadel, the primary goal is not just to secure services but to make the server itself invisible. I chose Cloudflare Tunnels over traditional reverse proxies like NPM or Caddy because it perfectly embodies the "Zero Trust" security model. It allows me to expose services to the internet without opening a single inbound port on my server's firewall.

**Core Advantages**:
*   **Zero-Attack-Surface Infrastructure**: The `cloudflared` daemon creates a secure, outbound-only connection to Cloudflare's network. This means my server has **no open ports** (like 80 or 443), making it completely invisible to public scanners and immune to direct network attacks like DDoS.
*   **IP Address Obfuscation**: My server's true IP address is never exposed to the public. All DNS records point to Cloudflare, providing a powerful layer of anonymity and protection.
*   **Integrated Access Control**: Cloudflare Tunnels seamlessly integrates with **Cloudflare Access**, allowing me to layer on robust, identity-based authentication (e.g., email PIN codes, Google/GitHub SSO) in front of any application. This ensures that only I can reach the login pages of my sensitive services.

**Alternatives Considered**:
*   `Nginx Proxy Manager`/`Caddy`: These are excellent reverse proxies for traditional IP-exposed setups. However, they require opening ports on the firewall, which fundamentally contradicts the goal of building a truly hidden, zero-trust environment. For services requiring ultimate privacy and security, the "invisible server" model of Cloudflare Tunnels is unbeatable.

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
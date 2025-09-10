<p align="right">
  <a href="./dashboard.md">English</a> | <a href="./dashboard_zh-CN.md">简体中文</a>
</p>

# Deep Dive: The Dashboard

The dashboard is the "grand foyer" of my digital citadel. Its purpose is to provide a single, centralized, and visually appealing entry point to all my self-hosted services, while also offering a quick overview of the system's status.

---

### 🧭 Control Panel: Homepage (gethomepage)

**Why I chose it**: In the realm of self-hosted dashboards, `Homepage` has rapidly become the community favorite, and for good reason. It combines a beautiful, modern aesthetic with incredibly powerful service integrations.

**Core Advantages**:
*   **Deep Service Integration (Widgets)**: This is Homepage's killer feature. It's not just a collection of bookmarks. Through its widget system, it connects directly to my other services' APIs (or the Docker socket) to display real-time information directly on the dashboard. I can see Uptime Kuma's status, the latest photos in Immich, or my server's current resource usage at a glance.
*   **Configuration as Code**: The entire dashboard is configured through simple, human-readable YAML files. This approach is intuitive for a developer, makes the configuration versionable (I check it into Gitea), and easy to back up.
*   **Aesthetic & Customizable**: It offers a clean, modern UI with support for themes, custom layouts, and a huge library of icons, allowing me to create a dashboard that is both functional and personal.
*   **Active Community**: The project is under very active development, with new service integrations and features being added constantly.

**Alternatives Considered**:
*   `Dashy`: A very capable and visually impressive alternative with a strong focus on UI customization through a graphical editor. However, I find Homepage's YAML-based configuration and its deeper, more extensive library of service integration widgets to be a better fit for my workflow.
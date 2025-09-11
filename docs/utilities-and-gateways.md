<p align="right">
  <a href="./utilities-and-gateways.md">English</a> | <a href="./utilities-and-gateways_zh-CN.md">简体中文</a>
</p>

# Deep Dive: Utilities & Gateways

This category comprises a set of specialized tools that serve as my personal gateways to the digital world or act as archives for valuable data. Each tool is chosen for its efficiency and dedication to a specific, well-defined task.

---

### 🎭 Anonymous Portal: SearXNG

**Why I chose it**: I believe that search is a fundamental gateway to information and should be free from corporate tracking and algorithmic bubbles. SearXNG is a powerful metasearch engine that acts as a privacy-respecting proxy between me and the wider internet.

**Core Advantages**:
*   **Decentralized Results**: SearXNG is not a search engine itself; it aggregates results from dozens of other engines. This prevents reliance on a single provider and offers a more diverse, less biased set of results.
*   **Privacy by Design**: The search engines I query only see requests coming from my server's IP, not from me personally. All tracking cookies, ads, and telemetry are stripped away.
*   **Extreme Customizability**: I can fine-tune which search engines are used, their weight, and create specific categories (e.g., a "Code" tab that only queries GitHub and StackOverflow).

**Alternatives Considered**:
*   `Whoogle`: A great, lightweight private frontend for Google. However, I prefer SearXNG's metasearch capability, as it aligns better with the goal of reducing dependence on any single tech giant.

---

### 📼 Video Archiver: MeTube

**Why I chose it**: The web is ephemeral. Valuable video content on platforms like YouTube or Bilibili can disappear without notice. MeTube provides a simple, server-side interface for `yt-dlp`, the definitive tool for archiving online videos.

**Core Advantages**:
*   **Leverages Server Resources**: It uses my VPS's fast and stable network connection to download videos, without consuming my local bandwidth.
*   **Simple Web UI**: It offers a convenient web interface to paste a URL, choose a format, and start a download, eliminating the need to SSH into the server to run a command.
*   **Broad Compatibility**: By using `yt-dlp` as its backend, it supports downloading from hundreds of different websites.

---

### 🗃️ Code Archive: Gitea

**Why I chose it**: As a developer, a personal Git server is essential. I chose Gitea over GitLab for its focus and efficiency. It does one thing—Git hosting—and does it exceptionally well with minimal resources.

**Core Advantages**:
*   **Lightweight & Fast**: Written in Go, Gitea is incredibly fast and has a very small memory footprint, making it ideal for a multi-service VPS.
*   **Core Features Included**: It provides all the essential features I need: repositories, issue tracking, pull requests, a wiki, and even CI/CD through Gitea Actions.
*   **Data Portability**: My repositories are stored in a standard Git format on my server's filesystem, making backups and potential migrations straightforward.

**Alternatives Considered**:
*   `GitLab`: An all-in-one DevOps platform. It is immensely powerful but also incredibly resource-heavy (requiring 4GB+ RAM just to idle). For personal projects, GitLab is overkill; Gitea provides the perfect balance of features and performance.

---

### ⭐ Code Curator: GitHub Stars Manager

**Why I chose it**: GitHub stars are a fantastic way to bookmark interesting projects, but they quickly become a chaotic, unsearchable black hole. Manual curation with lists is tedious and unsustainable. GitHub Stars Manager solves this by transforming my star history into an intelligent, searchable database. It acts as an automated curator, ensuring the valuable projects I discover are never lost.

**Core Advantages**:
*   **Automated Syncing**: Connects directly to my GitHub account to automatically pull in all starred repositories, new and old.
*   **AI-Powered Curation**: Uses AI to generate concise README summaries, tags, and relevant topics, saving hours of manual categorization.
*   **Semantic Search**: Allows me to find repositories based on what I *mean*, not just exact keywords, making discovery incredibly intuitive.
*   **Integrated Release Tracking**: Monitors repositories for new releases and provides one-click, filtered asset downloads (e.g., finding the `arm64.dmg` file instantly).

**Alternatives Considered**:
*   **Manual Tagging / GitHub Lists**: These methods are entirely manual, do not scale well, and lack features like AI summaries or release tracking. They require constant discipline rather than providing an automated solution.
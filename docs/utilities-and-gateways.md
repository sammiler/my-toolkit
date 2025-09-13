<p align="right">
  <a href="./utilities-and-gateways.md">English</a> | <a href="./utilities-and-gateways_zh-CN.md">简体中文</a>
</p>

# 🛠️ Deep Dive: Utilities & Gateways

This category comprises a set of specialized tools that serve as my personal gateways to the digital world, act as archives for valuable data, or provide essential swiss-army-knife functionality. Each tool is chosen for its efficiency and dedication to a specific, well-defined task.

---

### 🎭 Anonymous Portal: [SearXNG](https://docs.searxng.org/)

**Why I chose it**: I believe that search is a fundamental gateway to information and should be free from corporate tracking and algorithmic bubbles. SearXNG is a powerful metasearch engine that acts as a privacy-respecting proxy between me and the wider internet.

**Core Advantages**:
*   **Decentralized Results**: SearXNG is not a search engine itself; it aggregates results from dozens of other engines. This prevents reliance on a single provider and offers a more diverse, less biased set of results.
*   **Privacy by Design**: The search engines I query only see requests coming from my server's IP, not from me personally. All tracking cookies, ads, and telemetry are stripped away.
*   **Extreme Customizability**: I can fine-tune which search engines are used, their weight, and create specific categories (e.g., a "Code" tab that only queries GitHub and StackOverflow).

**Alternatives Considered**:
*   `Whoogle`: A great, lightweight private frontend for Google. However, I prefer SearXNG's metasearch capability, as it aligns better with the goal of reducing dependence on any single tech giant.

---

### 🚀 Hyperspace Tunnel: [Hysteria](https://hysteria.network/)

**Why I chose it**: In an era of network degradation and increasing internet fragmentation, I need a connection that is not only open but also exceptionally fast and resilient. Hysteria provides a high-performance tunnel designed to thrive in challenging network conditions, ensuring a smooth and unrestricted connection to the global internet.

**Core Advantages**:
*   **Built on QUIC Protocol**: Hysteria leverages the QUIC protocol (the basis for HTTP/3), which offers superior performance on unstable networks with high latency or packet loss.
*   **Advanced Censorship Resistance**: Its traffic is designed to masquerade as standard HTTP/3 traffic, making it incredibly difficult to detect and block.
*   **Exceptional Throughput**: It's engineered for speed, with a modern congestion control algorithm that allows it to rapidly saturate available bandwidth.

**Alternatives Considered**:
*   `WireGuard`: An excellent, fast, and modern VPN protocol. However, its distinct UDP signature can be an easy target for blocking without additional obfuscation.
*   `V2Ray/Xray`: The robust and reliable industry standard. I chose Hysteria for its superior performance on weak or high-latency networks.

---

### 📼 Video Archiver: [MeTube](https://github.com/alexta69/metube)

**Why I chose it**: The web is ephemeral. Valuable video content can disappear without notice. MeTube provides a simple, server-side interface for `yt-dlp`, the definitive tool for archiving online videos.

**Core Advantages**:
*   **Leverages Server Resources**: It uses my VPS's fast and stable network connection to download videos, without consuming my local bandwidth.
*   **Simple Web UI**: It offers a convenient web interface to paste a URL, choose a format, and start a download, eliminating the need to SSH into the server.
*   **Broad Compatibility**: By using `yt-dlp` as its backend, it supports downloading from hundreds of different websites.

---

### 🧰 Swiss Army Knife: [IT-Tools](https://it-tools.tech/)

**Why I chose it**: As a developer and tech enthusiast, I frequently need to perform small, one-off tasks like converting data formats, decoding tokens, generating hashes, or calculating subnet masks. IT-Tools consolidates dozens of these handy utilities into a single, clean, and fast web interface.

**Core Advantages**:
*   **All-in-One**: It brings together a vast collection of tools that would otherwise require searching online for separate, often ad-riddled websites.
*   **Privacy and Security**: By self-hosting, I can confidently paste sensitive data (like JWTs or private keys) into these tools without worrying about them being logged or transmitted over the internet.
*   **Works Offline**: Since it's a static web application, once loaded, it works entirely in the browser, making it incredibly fast and usable even without an active internet connection.

---

### 🗃️ Code Archive: [Gitea](https://gitea.io/)

**Why I chose it**: As a developer, a personal Git server is essential. I chose Gitea over GitLab for its focus and efficiency. It does one thing—Git hosting—and does it exceptionally well with minimal resources.

**Core Advantages**:
*   **Lightweight & Fast**: Written in Go, Gitea is incredibly fast and has a very small memory footprint, making it ideal for a multi-service VPS.
*   **Core Features Included**: It provides all the essential features I need: repositories, issue tracking, pull requests, a wiki, and even CI/CD through Gitea Actions.
*   **Data Portability**: My repositories are stored in a standard Git format on my server's filesystem, making backups and potential migrations straightforward.

**Alternatives Considered**:
*   `GitLab`: An all-in-one DevOps platform. It is immensely powerful but also incredibly resource-heavy. For personal projects, GitLab is overkill.

---

### ⭐ Code Curator: [GitHub Stars Manager](https://github.com/magical-universe/GitHub-Stars-Manager)

**Why I chose it**: GitHub stars are a fantastic way to bookmark interesting projects, but they quickly become a chaotic, unsearchable black hole. GitHub Stars Manager solves this by transforming my star history into an intelligent, searchable database. It acts as an automated curator, ensuring the valuable projects I discover are never lost.

**Core Advantages**:
*   **Automated Syncing**: Connects directly to my GitHub account to automatically pull in all starred repositories, new and old.
*   **AI-Powered Curation**: Uses AI to generate concise README summaries, tags, and relevant topics, saving hours of manual categorization.
*   **Semantic Search**: Allows me to find repositories based on what I *mean*, not just exact keywords, making discovery incredibly intuitive.
*   **Integrated Release Tracking**: Monitors repositories for new releases and provides one-click, filtered asset downloads.

**Alternatives Considered**:
*   **Manual Tagging / GitHub Lists**: These methods are entirely manual, do not scale well, and lack features like AI summaries or release tracking. They require constant discipline.
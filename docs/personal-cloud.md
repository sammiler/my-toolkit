<p align="right">
  <a href="./personal-cloud.md">English</a> | <a href="./personal-cloud_zh-CN.md">简体中文</a>
</p>

# ☁️ Deep Dive: Personal Cloud Services

This layer of my citadel is dedicated to managing my personal data. The guiding principle is 100% data ownership, replacing reliance on commercial cloud providers with robust, self-hosted alternatives. My strategy uses a two-pronged approach for file sync to cover different use cases.

---

### 📦 Sync Drive: [Nextcloud](https://nextcloud.com/)

**Role**: The centralized, "cloud-like" hub for general-purpose files, calendars, and contacts.

**Why I chose it**: While many lightweight file sync tools exist, Nextcloud offers a complete, integrated suite that goes far beyond simple file hosting. It's a powerful, open-source alternative to the ecosystems of Google Drive or iCloud.

**Core Advantages**:
*   **File Sync & Share**: Its core strength is providing reliable, cross-platform file synchronization. The web UI and sharing features make it feel like a true cloud service.
*   **Integrated Suite**: Beyond files, I use it for syncing my **Calendars** (CalDAV) and **Contacts** (CardDAV) directly with the native apps on my phone and computer. This creates a unified personal information management (PIM) system.
*   **App Ecosystem**: The vast library of Nextcloud Apps allows for future extensibility if my needs evolve.
*   **Mobile App**: The iOS/Android app is excellent, providing features like automatic photo uploads, which serves as a great entry point to data privatization.

---

### 🔗 Direct Conduit: [Syncthing](https://syncthing.net/)

**Role**: The decentralized, peer-to-peer workhorse for direct, high-speed sync between my trusted devices.

**Why I chose it**: Syncthing complements Nextcloud perfectly. Where Nextcloud is a centralized server, Syncthing is completely decentralized. It doesn't store anything in a central "cloud"; it synchronizes folders directly and securely between two or more of my computers. This is ideal for syncing large, frequently-changing folders (like code projects or virtual machine images) where I don't need a web interface or sharing links.

**Core Advantages**:
*   **Decentralized & Private**: There is no central server. Data travels directly between my devices, end-to-end encrypted. No third party ever has access to my data.
*   **Efficient & Fast**: It uses block-level synchronization, meaning only the changed parts of a file are transferred, making it incredibly efficient for large files.
*   **Resilient**: Because it's peer-to-peer, as long as two devices that share a folder are online, they will sync. It doesn't depend on my main VPS being available.

---

### 🖼️ Memories: [Immich](https://immich.app/)

**Role**: The intelligent, Google Photos replacement for a lifetime of photos and videos.

**Why I chose it**: Immich is a game-changer in the self-hosted photo management space. It's the first project to truly replicate—and in some ways, surpass—the intelligent features of Google Photos, all while running on your own hardware.

**Core Advantages**:
*   **Mobile-First Backup**: The primary focus is on seamless, automatic photo and video backup from mobile devices. The app is fast, reliable, and provides a great user experience.
*   **Private Machine Learning**: Immich performs all the "magic" locally on my VPS. This includes **face recognition** (grouping photos by person), **object/scene detection** (allowing me to search for "beach" or "cat"), and displaying photos on a world map based on location data.
*   **Multi-User & Sharing**: It has excellent support for partners and family members, with shared albums and a shared timeline view, making it a true replacement for commercial family photo solutions.
*   **Active Development**: The project is one of the most actively developed in the self-hosting community, with constant improvements and new features.
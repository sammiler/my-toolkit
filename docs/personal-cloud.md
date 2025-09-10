<p align="right">
  <a href="./personal-cloud.md">English</a> | <a href="./personal-cloud_zh-CN.md">简体中文</a>
</p>

# Deep Dive: Personal Cloud Services

This layer of my citadel is dedicated to managing my personal data. The guiding principle is 100% data ownership, replacing reliance on commercial cloud providers with robust, self-hosted alternatives.

---

### 📦 Sync Drive: Nextcloud

**Why I chose it**: While many lightweight file sync tools exist, Nextcloud offers a complete, integrated suite that goes far beyond simple file hosting. It's a powerful, open-source alternative to the ecosystems of Google Drive or iCloud.

**Core Advantages**:
*   **File Sync & Share**: Its core strength is providing reliable, cross-platform file synchronization. The desktop and mobile clients are mature and work seamlessly.
*   **Integrated Suite**: Beyond files, I use it for syncing my **Calendars** (CalDAV) and **Contacts** (CardDAV) directly with the native apps on my phone and computer. This creates a unified personal information management (PIM) system.
*   **App Ecosystem**: The vast library of Nextcloud Apps allows for future extensibility if my needs evolve.
*   **Mobile App**: The iOS/Android app is excellent, providing features like automatic photo uploads, which serves as a great entry point to data privatization.

**Alternatives Considered**:
*   `Syncthing`: A fantastic, lightweight, peer-to-peer file sync tool. However, it lacks the centralized, "cloud-like" features (web interface, sharing links, CalDAV/CardDAV) that I require from an all-in-one solution.

---

### 🖼️ Memories: Immich

**Why I chose it**: Immich is a game-changer in the self-hosted photo management space. It's the first project to truly replicate—and in some ways, surpass—the intelligent features of Google Photos, all while running on your own hardware.

**Core Advantages**:
*   **Mobile-First Backup**: The primary focus is on seamless, automatic photo and video backup from mobile devices. The app is fast, reliable, and provides a great user experience.
*   **On-Device Machine Learning**: Immich performs all the "magic" locally on my VPS. This includes **face recognition** (grouping photos by person), **object/scene detection** (allowing me to search for "beach" or "cat"), and displaying photos on a world map based on location data.
*   **Multi-User & Sharing**: It has excellent support for partners and family members, with shared albums and a shared timeline view, making it a true replacement for commercial family photo solutions.
*   **Active Development**: The project is one of the most actively developed in the self-hosting community, with constant improvements and new features.
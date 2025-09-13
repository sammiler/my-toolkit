<p align="right">
  <a href="./README.md">English</a> | <a href="./README_zh-CN.md">简体中文</a>
</p>

# 🏰 My Digital Citadel

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Status: Evolving](https://img.shields.io/badge/Status-Evolving-brightgreen)](https://github.com/your-username/my-citadel)
[![Docker Powered](https://img.shields.io/badge/Powered%20By-Docker-blue?logo=docker)](https://www.docker.com/)

> "The ultimate promise of technology is to make us masters of a world that we command by the push of a button." - Volker Grassmuck

This repository is the architectural blueprint for my personal digital citadel, a self-hosted ecosystem running on a private VPS. It documents the services I run, the philosophy behind my choices, and the workflows that connect them, all with a core focus on data ownership, privacy, and long-term utility.

---

## 🏛️ Service Architecture

My services are organized into logical layers, from foundational infrastructure to specialized workflows. Each component is containerized using Docker for portability, isolation, and ease of management.

### 🛡️ Infrastructure & Security

This is the bedrock of the citadel, ensuring all services are accessible, secure, and observable. Its stability is paramount.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 🚪 **Gateway** | **Cloudflare Tunnels** | The single, secure entry point for all services, handling SSL and routing. |
| 🔑 **Vault** | **Vaultwarden** | A hardened, self-hosted vault for all my digital credentials. |
| 🔭 **Watchtower** | **Uptime Kuma** | The vigilant eye, monitoring the health and uptime of every service. |
| 🚢 **Helm** | **Portainer** | The command deck, providing a powerful web UI to manage the entire Docker fleet. |

**➡️ [Learn more about my Infrastructure & Security setup](./docs/infrastructure-and-security.md)**

---

### 🧠 Knowledge Management

The core of my digital brain, designed for long-term knowledge retention and creation. This system separates the collection of raw materials from the synthesis of personal knowledge.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 📚 **Library** | **Zotero + hacdias/webdav** | For collecting, organizing, and annotating high-quality source materials (PDFs, web pages). |
| 📝 **Field Notes** | **Joplin** | For capturing, organizing, and drafting notes and ideas. The first stop for thoughts before they are synthesized. |
| 🧠 **Second Brain** | **Trilium Notes** | For synthesizing, linking, and creating my own networked knowledge base. |

**➡️ [Learn more about my Knowledge Management System](./docs/knowledge-management.md)**

---

### 🌊 Information Intake & Processing

This layer acts as my filter and funnel for the vast ocean of online information, turning chaotic streams into structured input for my knowledge base.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 📡 **Radar** | **FreshRSS** | An active radar for high-quality information, pulling from trusted sources without algorithmic noise. |
| 🍵 **Reading Room** | **Wallabag** | A quiet space for deep reading, stripping away distractions from articles saved for later. |

**➡️ [Learn more about my Information Intake Workflow](./docs/information-intake.md)**

---

### ☁️ Personal Cloud & Data

This is my private cloud, handling personal data from files to precious memories, ensuring complete ownership and privacy.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 📦 **Sync Drive** | **Nextcloud** | The versatile workhorse for file synchronization, calendars, and contacts across all my devices. |
| 🖼️ **Memories** | **Immich** | An intelligent, private gallery for a lifetime of photos and videos, with automatic mobile backup. |

**➡️ [Learn more about my Personal Cloud Services](./docs/personal-cloud.md)**

---
---

### 💾 Data Orchestration & Backup

This layer represents the nervous system of my data, responsible for secure backups, remote access, and seamless integration between my VPS and various cloud storage backends. This is where data resilience and accessibility are forged.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 🛡️ **Archivist** | **Kopia / Restic** | The master archivists, creating encrypted, deduplicated, and versioned backups of all critical data. |
| 🔗 **Connector** | **Rclone** | The universal translator, enabling access to a vast array of cloud storage services with a unified interface. |
| 🪩 **Mount Point** | **CloudDrive / Openlist** | The magic gateways that mount various cloud drives as local-like folders, simplifying data access. |

**➡️ [Learn more about my Data Orchestration & Backup Strategy](./docs/data-orchestration-and-backup.md)**

---

### 🛠️ Utilities & Gateways

A collection of powerful tools that enhance my digital life, from anonymous web exploration to video archiving.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 🎭 **Anonymous Portal** | **SearXNG** | My private gateway to the web, fetching aggregated search results without tracking. |
| 🚀 **Hyperspace Tunnel** | **Hysteria** | A powerful, lightning-fast, and censorship-resistant proxy for unrestricted internet access. |
| 📼 **Video Archiver** | **MeTube** | A server-side tool to permanently archive valuable videos from the web. |
| 🗃️ **Code Archive** | **Gitea** | A lightweight, fast forge for my personal code, scripts, and configurations. |
| ⭐ **Code Curator** | **GitHub Stars Manager** | An AI-powered dashboard to automatically sync, summarize, and categorize starred GitHub repos for easy discovery and release tracking. |

**➡️ [Learn more about my Utilities & Gateways](./docs/utilities-and-gateways.md)**

---

### 🖥️ The Dashboard

The grand foyer of my citadel, providing a single pane of glass to access and view the status of all services.

| Role | Toolchain | Purpose |
| :--- | :--- | :--- |
| 🧭 **Control Panel** | **Homepage** | A beautiful, highly integrated dashboard that serves as my launchpad and system overview. |

**➡️ [Learn more about my Dashboard Philosophy](./docs/dashboard.md)**
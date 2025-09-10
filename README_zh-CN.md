<p align="right">
  <a href="./README.md">English</a> | <a href="./README_zh-CN.md">简体中文</a>
</p>

# 🏰 我的数字城堡

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Status: Evolving](https://img.shields.io/badge/Status-Evolving-brightgreen)](https://github.com/your-username/my-citadel)
[![Docker Powered](https://img.shields.io/badge/Powered%20By-Docker-blue?logo=docker)](https://www.docker.com/)

> "技术的终极承诺，是让我们成为一个只需按下按钮即可掌控的世界的主人。" - 沃尔克·格拉斯穆克 (Volker Grassmuck)

本仓库是我的个人数字城堡的架构蓝图，这是一个运行于私有VPS上的自托管生态系统。它记录了我所运行的服务、选择背后的理念以及将它们连接在一起的工作流，其核心完全围绕数据所有权、隐私和长期效用。

---

## 🏛️ 服务架构

我的服务被组织成逻辑分明的层次，从基础架构到专业化的工作流。每个组件都使用 Docker 进行容器化，以实现可移植性、隔离性和易管理性。

### 🛡️ 基础设施与安全

这是城堡的基石，确保所有服务都可被访问、安全且可观测。其稳定性至关重要。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🚪 **网关 (Gateway)** | **Nginx Proxy Manager** | 所有服务的单一、安全入口，处理SSL和路由。 |
| 🔑 **金库 (Vault)** | **Vaultwarden** | 一个强化的、自托管的保险库，用于存放我所有的数字凭证。 |
| 🔭 **瞭望塔 (Watchtower)** | **Uptime Kuma** | 警惕之眼，监控每个服务的健康状况和在线时间。 |

**➡️ [深入了解我的基础设施与安全选型](./docs/infrastructure-and-security_zh-CN.md)**

---

### 🧠 知识管理

我数字大脑的核心，为长期的知识沉淀与创造而设计。该系统将原始材料的收集与个人知识的合成相分离。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📚 **图书馆 (Library)** | **Zotero + hacdias/webdav** | 用于收集、组织和批注高质量的原始资料（PDF、网页）。 |
| 🧠 **第二大脑 (Second Brain)** | **Trilium Notes** | 用于合成、链接并创建我自己的网络化知识库。 |

**➡️ [深入了解我的知识管理体系](./docs/knowledge-management_zh-CN.md)**

---

### 🌊 信息获取与处理

该层扮演着我面对浩瀚网络信息的过滤器和漏斗，将混乱的信息流转化为我知识库的结构化输入。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📡 **雷达 (Radar)** | **FreshRSS** | 一个主动的高质量信息雷达，从可信来源拉取信息，不受算法噪音干扰。 |
| 🍵 **阅览室 (Reading Room)** | **Wallabag** | 一个用于深度阅读的安静空间，剥离干扰，专注于稍后阅读的文章。 |

**➡️ [深入了解我的信息获取工作流](./docs/information-intake_zh-CN.md)**

---

### ☁️ 个人云与数据

这是我的私有云，处理从文件到珍贵回忆的个人数据，确保完全的所有权和隐私。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📦 **同步盘 (Sync Drive)** | **Nextcloud** | 功能丰富的主力工具，用于在我所有设备间同步文件、日历和联系人。 |
| 🖼️ **回忆相册 (Memories)** | **Immich** | 一个智能化的私有相册，用于存放一生的照片和视频，并支持移动端自动备份。 |

**➡️ [深入了解我的个人云服务](./docs/personal-cloud_zh-CN.md)**

---

### 🛠️ 效率工具与网关

一系列强大的工具，用于增强我的数字生活，从匿名网页探索到视频存档。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🎭 **匿名门户 (Anonymous Portal)** | **SearXNG** | 我的私有网页入口，在不被追踪的情况下获取聚合搜索结果。 |
| 📼 **视频存档器 (Video Archiver)** | **MeTube** | 一个服务器端工具，用于永久存档来自网络的珍贵视频。 |
| 🗃️ **代码档案馆 (Code Archive)** | **Gitea** | 一个轻量、快速的代码托管平台，用于存放我的个人代码、脚本和配置。 |

**➡️ [深入了解我的效率工具与网关](./docs/utilities-and-gateways_zh-CN.md)**

---

### 🖥️ 仪表盘

我的数字城堡的宏伟大厅，提供一个单一的玻璃面板来访问和查看所有服务的状态。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🧭 **控制面板 (Control Panel)** | **Homepage** | 一个美观、高度集成的仪表盘，作为我的启动台和系统概览。 |

**➡️ [深入了解我的仪表盘理念](./docs/dashboard_zh-CN.md)**
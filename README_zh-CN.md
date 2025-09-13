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
| 🚪 **网关 (Gateway)** | **Cloudflare Tunnels** | 从互联网进入城堡的单一、安全入口。 |
| 🚦 **调度员 (Dispatcher)** | **Pangolin** | 内部交通指挥，一个将请求路由到正确服务的反向代理。 |
| 🔑 **金库 (Vault)** | **Vaultwarden** | 一个强化的、自托管的保险库，用于存放我所有的数字凭证。 |
| 🔭 **哨兵 (Sentinel)** | **Uptime Kuma** | 警惕的守卫，监控每个对外服务的健康状况和在线时间。 |
| 🩺 **医师 (Physician)** | **Netdata** | 城堡的医师，为系统和应用健康提供实时、高精度的诊断。 |
| ⚙️ **军需官 (Quartermaster)** | **Watchtower** | 勤勉的供给官，确保所有服务都自动更新到最新的安全版本。 |
| 🚢 **舵手 (Helm)** | **Portainer** | 指挥甲板，提供一个强大的Web界面来管理整个Docker舰队。 |

**➡️ [深入了解我的基础设施与安全选型](./docs/infrastructure-and-security_zh-CN.md)**

---

### 🧠 知识管理

我数字大脑的核心，为长期的知识沉淀与创造而设计。该系统将原始材料的收集与个人知识的合成相分离。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📚 **图书馆 (Library)** | **Zotero + hacdias/webdav** | 用于收集、组织和批注高质量的原始资料。 |
| 📝 **工作台 (Workbench)** | **Joplin** | 用于捕捉、组织和起草笔记与想法。是思想在被提炼前的第一站。 |
| 🧠 **第二大脑 (Second Brain)** | **Trilium Notes** | 用于合成、链接并创建我自己的网络化知识库。 |

**➡️ [深入了解我的知识管理体系](./docs/knowledge-management_zh-CN.md)**

---

### 🌊 信息获取与处理

该层扮演着我面对浩瀚网络信息的过滤器和漏斗，将混乱的信息流转化为我知识库的结构化输入。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📡 **雷达 (Radar)** | **FreshRSS** | 一个主动的高质量信息雷达，从可信来源拉取信息，不受算法噪音干扰。 |
| 🍵 **阅览室 (Reading Room)** | **Wallabag** | 一个用于深度阅读的安静空间，剥离干扰，专注于稍后阅读的文章。 |
| 🕵️ **侦察兵 (Scout)** | **ChangeDetection.io** | 一位警惕的侦察兵，监控网站内容变化并及时发出警报。 |

**➡️ [深入了解我的信息获取工作流](./docs/information-intake_zh-CN.md)**

---

### 📢 发布与内容创作

这里是城堡的公共喉舌，用于将整理后的知识和原创思考分享给世界。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📣 **信使 (Herald)** | **Ghost** | 城堡的官方喉舌，一个用于发布文章和新闻通讯的现代化平台。 |

**➡️ [深入了解我的发布工作流](./docs/publishing-and-content-creation_zh-CN.md)**

---

### ☁️ 个人云与数据

这是我的私有云，处理从文件到珍贵回忆的个人数据，确保完全的所有权和隐私。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 📦 **同步盘 (Sync Drive)** | **Nextcloud** | 功能丰富的主力工具，用于在我所有设备间同步文件、日历和联系人。 |
| 🔗 **直连管道 (Direct Conduit)** | **Syncthing** | 一款去中心化的、点对点的文件同步服务，用于在受信任设备间直接传输数据。 |
| 🖼️ **回忆相册 (Memories)** | **Immich** | 一个智能化的私有相册，用于存放一生的照片和视频，并支持移动端自动备份。 |

**➡️ [深入了解我的个人云服务](./docs/personal-cloud_zh-CN.md)**

---

### 💾 数据编排与备份

该层代表我数据的“神经系统”，负责安全备份、远程访问以及在我的VPS和各种云存储后端之间的无缝集成。数据的弹性和可访问性在此得以铸就。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🛡️ **档案馆员 (Archivist)** | **Kopia / Restic / Duplicati** | 首席档案馆员，为所有关键数据创建加密、去重和版本化的备份。 |
| 🔗 **连接器 (Connector)** | **Rclone** | 通用翻译器，通过统一的接口实现对众多云存储服务的访问。 |
| 🪩 **挂载点 (Mount Point)** | **CloudDrive / Openlist** | 神奇的网关，将各种云盘挂载为类似本地的文件夹，简化数据访问。 |

**➡️ [深入了解我的数据编排与备份策略](./docs/data-orchestration-and-backup_zh-CN.md)**

---

### 🛠️ 工具与网关

一系列增强我数字生活的强大工具，从匿名网络探索到视频归档。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🎭 **匿名门户** | **SearXNG** | 我的私人网络入口，聚合搜索结果且不被追踪。 |
| 🚀 **超空间隧道** | **Hysteria** | 一款强大、高速且抗审查的代理，用于实现无限制的互联网访问。 |
| 📼 **视频存档器** | **MeTube** | 一款服务器端工具，用于永久存档来自网络的珍贵视频。 |
| 🧰 **瑞士军刀 (Swiss Army Knife)** | **IT-Tools** | 一个自托管的、将各种便捷的开发者和IT工具集于一身的瑞士军刀。 |
| 🗃️ **代码档案** | **Gitea** | 一个为我的个人代码、脚本和配置准备的轻量、快速的代码托管服务。 |
| ⭐ **代码策展人** | **GitHub Stars Manager** | 一个 AI 驱动的仪表盘，用于自动同步、总结和分类加星的 GitHub 仓库。 |

**➡️ [进一步了解我的工具与网关](./docs/utilities-and-gateways_zh-CN.md)**

---

### 🖥️ 仪表盘

我的数字城堡的宏伟大厅，提供一个单一的玻璃面板来访问和查看所有服务的状态。

| 角色 | 工具链 | 用途 |
| :--- | :--- | :--- |
| 🧭 **控制面板 (Control Panel)** | **Homepage** | 一个美观、高度集成的仪表盘，作为我的启动台和系统概览。 |

**➡️ [深入了解我的仪表盘理念](./docs/dashboard_zh-CN.md)**
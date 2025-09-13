<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# 🛡️ 基础设施与安全：深度解析

本文档详细拆解了我的数字城堡基础层背后的理念、工具和工作流。主 `README.md` 中对此有简要概述。

### 核心理念：零信任、完全可观测性 & 自动化维护

整个城堡的安全与稳定都建立在这个基础之上。我的方法遵循三大核心原则：

1.  **零信任访问 (Zero Trust Access)**：任何服务都永远不会直接暴露于公共互联网。每一个请求都必须通过一个单一的、经过身份验证的加密网关。
2.  **完全可观测性 (Total Observability)**：我无法保护我看不见的东西。这意味着需要从多个维度来审视城堡的健康状况：从外部是否可达到内部的性能指标。
3.  **自动化维护 (Automated Maintenance)**：城堡应尽可能地自我维护。安全补丁和功能更新应被自动应用，以最大限度地缩短漏洞窗口期。

---

### 工具详解

#### 🚪 网关: [Cloudflare Tunnels](https://www.cloudflare.com/products/tunnel/)

*   **为何选择 Cloudflare Tunnels?**: 它完美地体现了零信任原则。它从我的VPS到Cloudflare网络创建了一个安全的、仅出站的连接。我的服务器IP地址和开放端口对互联网完全隐藏，从而消除了巨大的攻击面。

#### 🚦 调度员: [Pangolin](https://github.com/fosrl/pangolin)

*   **为何选择 Pangolin?**: 它扮演着城堡内部交通指挥的角色。当 Cloudflare Tunnels 将流量安全地带*到*我的服务器后，Pangolin 就接管了后续工作。它是一个带有简洁 Web 界面的增强版 Nginx 反向代理。它根据主机名将传入的请求路由到正确的 Docker 容器，管理内部 SSL，并极大地简化了原本复杂的 Nginx 配置文件。

#### 🔑 金库: [Vaultwarden](https://github.com/dani-garcia/vaultwarden)

*   **为何选择 Vaultwarden?**: 这是一个轻量级的Bitwarden API开源实现。它提供了一个现代密码管理器所需的所有核心功能。作为我数字生活的主密钥，自托管是不可协商的。

#### 🔭 哨兵: [Uptime Kuma](https://github.com/louislam/uptime-kuma)

*   **为何选择 Uptime Kuma?**: 它提供了我服务的“外部视角”。它是我警惕的守卫，监控着每一个对外暴露的服务以确保其正常响应。其丰富的通知系统确保一旦有服务宕机，我能第一时间知晓。

#### 🩺 医师: [Netdata](https://www.netdata.cloud/)

*   **为何选择 Netdata?**: 它提供了至关重要的“内部视角”。Uptime Kuma 告诉我服务*是否*宕机，而 Netdata 则告诉我*为什么*。它能实时自动发现并监控一切，从宿主操作系统的CPU到单个Docker容器，这对于排查问题至关重要。

#### ⚙️ 军需官: [Watchtower](https://containrrr.dev/watchtower/)

*   **为何选择 Watchtower?**: 这个工具体现了“自动化维护”原则。它在后台运行，并持续监控我正在运行的 Docker 容器。当它检测到镜像的新版本被推送到镜像仓库时，它会自动拉取新镜像并平滑地重启相应的容器。这确保了我总能以零手动干预的方式，运行着所有服务的最新、最安全的版本。

#### 🚢 舵手: [Portainer](https://www.portainer.io/)

*   **为何选择 Portainer?**: 这是我的指挥甲板。Portainer 的 Web 界面为我的整个 Docker 环境提供了一个卓越的“管理视角”。它简化了诸如部署堆栈、管理卷、以及检查容器日志等复杂任务，是日常运营不可或缺的工具。
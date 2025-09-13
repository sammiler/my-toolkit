<p align="right">
  <a href="./infrastructure-and-security.md">English</a> | <a href="./infrastructure-and-security_zh-CN.md">简体中文</a>
</p>

# 🛡️ 基础设施与安全：深度解析

本文档详细拆解了我的数字城堡基础层背后的理念、工具和工作流。主 `README.md` 中对此有简要概述。

### 核心理念：零信任 & 完全可观测性

整个城堡的安全与稳定都建立在这个基础之上。我的方法遵循两大核心原则：

1.  **零信任访问 (Zero Trust Access)**：任何服务都永远不会直接暴露于公共互联网。每一个请求，无一例外，都必须通过一个单一的、经过身份验证的加密网关。内部网络在默认情况下被视为是充满敌意的。
2.  **完全可观测性 (Total Observability)**：我无法保护我看不见的东西。这意味着需要从多个维度来审视城堡的健康状况：
    *   **外部视角 (在线状态)**：从外部世界看，服务是否可达？
    *   **内部视角 (性能表现)**：服务及其底层系统的性能如何？是否存在任何资源瓶颈或异常？
    *   **管理视角 (控制能力)**：我能否轻松地管理所有服务的生命周期？

---

### 工具详解

#### 🚪 网关: [Cloudflare Tunnels](https://www.cloudflare.com/products/tunnel/)

*   **为何选择 Cloudflare Tunnels?**: 它完美地体现了零信任原则。它从我的VPS到Cloudflare网络创建了一个安全的、仅出站的连接。我的服务器IP地址和开放端口对互联网完全隐藏，从而消除了巨大的攻击面。它还免费提供了世界级的DDoS保护和全球CDN。

#### 🔑 金库: [Vaultwarden](https://github.com/dani-garcia/vaultwarden)

*   **为何选择 Vaultwarden?**: 这是一个用Rust编写的、轻量级的Bitwarden API开源实现。它提供了我所需要的所有核心功能——安全的密码存储、生成和跨设备同步——而没有官方自托管服务器的资源开销。它是我整个数字生活的主密钥，因此自托管是不可协商的。

#### 🔭 瞭望塔: [Uptime Kuma](https://github.com/louislam/uptime-kuma)

*   **为何选择 Uptime Kuma?**: 它提供了我服务的“外部视角”。它的设置极其简单，并拥有一个美观、直观的用户界面。它不仅能监控HTTP(s)端点，还能监控特定端口，甚至检查页面上的关键字。其丰富的通知系统确保一旦城堡的“外墙”出现任何破损或无响应，我能第一时间知晓。

#### 🩺 医师: [Netdata](https://www.netdata.cloud/)

*   **为何选择 Netdata?**: 它提供了至关重要的“内部视角”。Uptime Kuma 告诉我服务*是否*宕机，而 Netdata 则告诉我它*为什么*可能陷入困境。它能实时自动发现并监控一切——从宿主操作系统的CPU和内存，到单个Docker容器的资源使用情况。其高精度的、每秒更新的指标对于排查性能问题具有不可估量的价值。对于单节点部署，它的简易性和强大功能远胜于配置复杂的 Prometheus/Grafana 栈。

#### 🚢 舵手: [Portainer](https://www.portainer.io/)

*   **为何选择 Portainer?**: 这是我的指挥甲板。虽然我熟悉命令行操作，但 Portainer 的 Web 界面为我的整个 Docker 环境提供了一个卓越的“管理视角”。它简化了诸如部署堆栈、管理卷和网络、以及检查容器日志等复杂任务。它是日常运营和管理不可或缺的工具。
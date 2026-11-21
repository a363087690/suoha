# suoha

## suoha-ai（推荐，2026 版）

一键部署 VLESS + Vision + REALITY（主）和 Hysteria2（备）双通道代理。

```bash
curl -fsSL https://raw.githubusercontent.com/a363087690/suoha/main/suoha-ai.sh -o suoha-ai.sh && bash suoha-ai.sh
```

- 主通道：VLESS + Vision + REALITY，TCP 443，无需域名和证书
- 备通道：Hysteria2，UDP 8443，QUIC，自签证书 + pinSHA256
- 自动测速选择 REALITY 伪装目标、自动处理端口占用、自动启用 BBR
- 生成 Clash Meta 自动择优配置：`/etc/suoha/clash-meta.yaml`
- 要求：root、systemd、公网 IPv4/IPv6；放行 TCP 443 和 UDP 8443
- 管理：`bash suoha-ai.sh --status | --links | --update | --uninstall --yes`

> 基于 2023 年的 suoha 脚本重写，原项目已停止更新。仅供个人学习与合法的网络访问使用。

---

## 旧版脚本（2023，已停更）

### alpine 安装 argo（vless & vmess）

```bash
wget https://raw.githubusercontent.com/a363087690/suoha-reality/main/suoha.sh -O suoha.sh && bash suoha.sh
```

信息保存在 `v2ray.txt`，再次查看：

```bash
cat v2ray.txt
```

### alpine 搭建 reality 协议

```bash
apk update && apk add bash && wget https://raw.githubusercontent.com/a363087690/suoha-reality/main/reality.sh -O reality.sh && bash reality.sh
```

# Rule-Factory-Provider

本项目以网上公开的规则和域名列表作为候选及命名参考。维护者在自有家宽和境内外服务器上进行私人验证与清洗，再逐步发布当前证据满足条件的个人规则组。

当前内容仅包含通过条件的 HOME 精确域名规则文件。候选来源中的其他条目并不因此代表已经验证或适合使用。网络可达性也不能证明账号可以登录或服务能够解锁；验证结果会随时间、网络和服务变化。

HTTP provider 预计每 6 小时检查更新；设备离线或拉取失败时，客户端可能继续使用缓存。请结合自己的网络环境审查和使用。

## 订阅

以下是合入现有 Mihomo 配置的片段，不是完整配置。将 provider 加入现有 `rule-providers`，并将规则插入原有 Netflix 规则之后：

```yaml
rule-providers:
  OwnHomeVerified:
    type: http
    behavior: classical
    format: yaml
    url: https://raw.githubusercontent.com/spaceerotic/Rule-Factory-Provider/main/rules/home-direct-verified.yaml
    path: ./rules/own/home-direct-verified.yaml
    interval: 21600

rules:
  - GEOSITE,netflix,Netflix
  - RULE-SET,OwnHomeVerified,DIRECT
```

感谢公开来源的原作者、维护者和社区的工作。本项目由个人维护，不代表上游官方，也不冒充其发布；上游作品的归属和许可要求应予保留。来源与许可原文链接见 [SOURCES.md](SOURCES.md) 和 [NOTICE.md](NOTICE.md)。

# 简介

本项目生成适用于 [**Clash Premium 内核**](https://github.com/Dreamacro/clash/releases/tag/premium)的规则集（RULE-SET），同时适用于所有使用 Clash Premium 内核的 Clash 图形用户界面（GUI）客户端。使用 GitHub Actions 北京时间每天早上 6:30 自动构建，保证规则最新。




### 使用方式

要想使用本项目的规则集，只需要在 Clash 配置文件中添加如下 `rule-providers` 和 `rules`。

#### Rule Providers 配置方式

```yaml
  Myrejetct:
    type: http
    behavior: domain
    url: https://anti-ad.net/clash.yaml
    path: ./ruleset/Myrejetct.yaml
    interval: 259200
  cncidr:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/DH-Teams/DH-Geo_AS_IP_CN/main/Geo_AS_IP_CN_All_Clash.yaml
    path: ./ruleset/cncidr.yaml
    interval: 259200

  proxy:
    type: http
    behavior: domain
    url:  https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/proxy.txt
    path: ./ruleset/proxy.yaml
    interval: 259200
  direct:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/direct.txt
    path: ./ruleset/direct.yaml
    interval: 259200
  cfdomain:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/cf-domain.txt
    path: ./ruleset/cfdomain.yaml
    interval: 259200
    
  openai:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/openai.txt
    path: ./ruleset/openai.yaml
    interval: 259200    

  lancidr:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/kurdsvv/rules/master/Clash-Rule/lancidr.txt
    path: ./ruleset/lancidr.yaml
    interval: 259200
  telegramcidr:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/kurdsvv/rules/master/Clash-Rule/telegramcidr.txt
    path: ./ruleset/telegramcidr.yaml
    interval: 259200

  DropIP:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/DropIP.txt
    path: ./ruleset/DropIP.yaml
    interval: 259200

  private:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/private.txt
    path: ./ruleset/private.yaml
    interval: 259200
  reject:
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/Reject.txt
    path: ./ruleset/reject.yaml
    interval: 259200
  Cloudflare:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/Cloudflare.txt
    path: ./ruleset/Cloudflare.yaml
    interval: 259200
  Google:
    type: http
    behavior: ipcidr
    url: https://raw.githubusercontent.com/kurdsvv/rules/master/Clash-Rule/Google.txt
    path: ./ruleset/Google.yaml
    interval: 259200
  applications:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/applications.txt
    path: ./ruleset/applications.yaml
    interval: 259200

  icloud:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/icloud.txt"
    path: ./ruleset/icloud.yaml
    interval: 86400

  apple:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/kurdsvv/rules/refs/heads/master/Clash-Rule/apple.txt"
    path: ./ruleset/apple.yaml
    interval: 86400
```

#### 白名单模式 Rules 配置方式（推荐）

- 白名单模式，意为「**没有命中规则的网络流量，统统使用代理**」，适用于服务器线路网络质量稳定、快速，不缺服务器流量的用户。
- 以下配置中，除了 `DIRECT` 和 `REJECT` 是默认存在于 Clash 中的 policy（路由策略/流量处理策略），其余均为自定义 policy，对应配置文件中 `proxies` 或 `proxy-groups` 中的 `name`。如你直接使用下面的 `rules` 规则，则需要在 `proxies` 或 `proxy-groups` 中手动配置一个 `name` 为 `PROXY` 的 policy。
- 如你希望 Apple、iCloud 和 Google 列表中的域名使用代理，则把 policy 由 `DIRECT` 改为 `PROXY`，以此类推，举一反三。
- 如你不希望进行 DNS 解析，可在 `GEOIP` 规则的最后加上 `,no-resolve`，如 `GEOIP,CN,DIRECT,no-resolve`。

```yaml
  - RULE-SET,DropIP,REJECT-DROP
  - RULE-SET,reject,REJECT
  - RULE-SET,applications,REJECT
  #- RULE-SET,Myrejetct,REJECT
  - RULE-SET,proxy,🚀 节点选择
  - RULE-SET,private,♻️ 自动选择
  - RULE-SET,openai,♻️ 自动选择
  - RULE-SET,telegramcidr,🌈 Telegram
  - RULE-SET,direct,DIRECT
  - RULE-SET,cncidr,DIRECT
  - RULE-SET,icloud,DIRECT
  - RULE-SET,apple,DIRECT
  - RULE-SET,Google,🚀 节点选择
  - RULE-SET,Cloudflare,Cloudafare-conn
  - RULE-SET,lancidr,DIRECT
  - MATCH,MATCH
```




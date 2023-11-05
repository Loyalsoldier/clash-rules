# 简介

由于 Clash 及其部分周边生态项目于 2023 年 11 月上旬删库跑路，现提供部分官方原版安装包、可执行文件。

- [Clash v1.18.0 源码压缩包](https://github.com/Loyalsoldier/clash-rules/blob/hidden/software/src)（可构建出以下 **Clash 命令行版**）
- **命令行版**：
  - [Clash](https://github.com/Loyalsoldier/clash-rules/blob/hidden/software/clash)（适用于 Windows、macOS、Linux）
  - [Clash Premium](https://github.com/Loyalsoldier/clash-rules/blob/hidden/software/clash-premium)（适用于 Windows、macOS、Linux）
- 使用 Clash Premium 作为内核的**图形用户界面版**：
  - [ClashX Pro](https://github.com/Loyalsoldier/clash-rules/blob/hidden/software/clashx-pro)（适用于 macOS）
  - [Clash for Windows](https://github.com/Loyalsoldier/clash-rules/blob/hidden/software/clash-for-windows)（适用于 Windows）

以上部分资源可在[**互联网档案馆时光机**](https://web.archive.org)中找到，网址如下：

- **@Dreamacro/Clash**:
  - [仓库](https://web.archive.org/web/20231102080544/https://github.com/Dreamacro/clash)
  - [命令行版软件发布页](https://web.archive.org/web/20231102080544/https://github.com/Dreamacro/clash/releases)
  - [Premium 命令行版软件发布页](https://web.archive.org/web/20231102080403/https://github.com/Dreamacro/clash/releases/tag/premium)
- **@yichengchen/ClashX**:
  - [仓库](https://web.archive.org/web/20231103085620/https://github.com/yichengchen/clashX)
  - [软件发布页](https://web.archive.org/web/20231103102433/https://github.com/yichengchen/clashX/releases)
- **@Fndroid/Clash for Windows**：
  - [软件发布页](https://web.archive.org/web/20231101083947/https://github.com/Fndroid/clash_for_windows_pkg/releases)

## 构建适用于本机的 Clash 命令行版

1. 下载上方列出的 Clash 源码压缩包后，解压
2. 安装 Go 运行时
3. 在源码解压目录内，运行命令：`go build ./`
4. 目录内的 `Clash` 或 `Clash.exe` 即为适用于本机的 Clash 命令行版

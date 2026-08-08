<p align="center">
  <img src="entryway_logo.png" alt="Entryway Logo" width="120">
</p>

<p align="center"><strong>Entryway</strong></p>
<p align="center">多服务器聚合管理的跨平台媒体客户端，支持 Jellyfin 和 Emby。</p>
<p align="center">A multi-server aggregation media client for Jellyfin & Emby — Android, Android TV & Windows.</p>
<p align="center"><a href="https://www.yamby.cn">官方网站 | Official Website</a></p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android%20%7C%20Android_TV%20%7C%20Windows-3DDC84?style=flat-square" alt="Platform">
  <img src="https://img.shields.io/badge/Server-Jellyfin%20%7C%20Emby-AA0000?style=flat-square" alt="Server">
  <img src="https://img.shields.io/badge/License-MIT-blue?style=flat-square" alt="License">
</p>

---

## 最新版本 | Latest Release

**全局标签 `v0.20.0`**（各端应用版本独立）

| 平台 | 应用版本 | 构建号 | 下载 |
| --- | --- | --- | --- |
| Android 手机版 | 0.20.0 | 40 | [`entryway-release-0.20.0.apk`](https://gitea.yamby.cn/yusheng/Entryway_Release/releases/download/v0.20.0/entryway-release-0.20.0.apk) |
| Android TV 版 | 0.18.0 | 38 | [`Entryway-tv-release-0.18.0.apk`](https://gitea.yamby.cn/yusheng/Entryway_Release/releases/download/v0.20.0/Entryway-tv-release-0.18.0.apk) |
| Windows x64 | 0.18.0 | 37 | [`Entryway_0.18.0+37_Windows_x64_Setup.exe`](https://gitea.yamby.cn/yusheng/Entryway_Release/releases/download/v0.20.0/Entryway_0.18.0+37_Windows_x64_Setup.exe) |

> Android 手机版与 TV 版沿用 1.0 前的调试证书签名约定，Windows 安装包未签名；首次运行可能触发系统安全提示，需手动确认。
>
> ⚠️ v0.19.0 的手机安装包误用了正式发布证书，无法覆盖安装。0.18.x 及更早版本可直接覆盖安装 0.20.0；若已安装 v0.19.0，需先卸载再安装。

- **变更日志**：[`RELEASE_NOTES.md`](RELEASE_NOTES.md)
- **全部版本**：[Gitea Releases](https://gitea.yamby.cn/yusheng/Entryway_Release/releases) ｜ [GitHub Releases](https://github.com/JackYucongjia/Entryway_Release/releases)

## 概述 | Overview

**Entryway** 是一个面向自建媒体服务器用户的跨平台客户端，覆盖 **Android 手机**、**Android TV** 和 **Windows** 三端。核心设计理念是 **多服务器聚合**——在一个统一的界面中管理和浏览你所有的 Jellyfin / Emby 服务器。

Entryway is a cross-platform client for self-hosted media server users, available on **Android Mobile**, **Android TV**, and **Windows**. Its core philosophy is **multi-server aggregation** — managing and browsing all your Jellyfin / Emby servers from a single, unified interface.

**官网**：[www.yamby.cn](https://www.yamby.cn)

## 核心特性 | Features

### 🖥️ 多服务器管理
- 添加多个 Jellyfin / Emby 服务器，一键快速切换
- 服务器卡片显示用户头像、用户名、服务器地址
- 私密服务器：标记后默认隐藏，需手动开启显示
- 冷启动离线恢复：服务器不可用时不清除账号

### 🎬 双引擎播放器（Android）
- **ExoPlayer**：默认引擎，基于 Media3 + FFmpeg 扩展
- **mpv**：高兼容性引擎，含 libdvdread/libdvdnav/libbluray
- 自动容错切换，保留播放进度
- 解码模式：SW / HW / HW+ / DV-SW

### 💬 多弹幕服务
- 弹弹Play 官方、LogVar 弹幕 API、其他弹弹Play 兼容服务
- 按优先级有序故障回退，数据源严格隔离
- 自动匹配、手动搜索、本地弹幕、LRU 缓存
- 三端支持（手机 / TV / Windows）

### 💿 实验性 DVD / Blu-ray ISO
- 未加密原盘本地与远程播放
- 不支持时自动回退服务器转码

### 📺 Android TV
- 遥控器全键盘搜索、二维码手机输入
- 完整弹幕、扫码录入服务器、首页缓存兜底

### 🪟 Windows
- Flutter + MediaKit (libmpv) + Rust 弹幕引擎
- 多服务器、收藏、详情、跨服搜索、离线下载
- Chromecast/DLNA 投屏、Inno Setup 安装器

### 🎨 设计与国际化
- 空间化 / 玻璃态视觉语言，Material 3 动态配色
- 完整中文（简体/繁体）和英文本地化

### 📥 离线下载
- 队列化管理，批量下载，存储空间预估
- 无网络时自动切换离线内容模式

## 平台要求 | Requirements

| 平台 | 最低要求 |
| --- | --- |
| Android 手机版 | Android 8.1 (API 27) |
| Android TV 版 | Android 8.1 (API 27) |
| Windows | Windows 10 x64 |

## 更新检测 | Update Check

客户端内置更新检测，优先从 Gitea 获取最新版本，连接失败时自动降级到 GitHub。

## 源码仓库 | Source Code

- **GitHub**：[github.com/JackYucongjia/Entryway](https://github.com/JackYucongjia/Entryway)
- **Gitea**：[gitea.yamby.cn/yusheng/Entryway](https://gitea.yamby.cn/yusheng/Entryway)

## 许可证 | License

本项目基于 MIT 许可证开源。

手机端弹幕实现参考了 MIT 许可的 [AimesSoft/NipaPlay-Reload](https://github.com/AimesSoft/NipaPlay-Reload)。
Windows 客户端基于 NipaPlay-Reload `v1.10.13` 构建，保留上游 MIT 许可。

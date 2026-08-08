# Entryway v0.20.0

本批次同步发布 Android 手机版、Android TV 和 Windows x64。各端应用版本独立维护：Mobile `0.20.0`、TV `0.18.0`、Windows `0.18.0+37`。

## 版本信息

| 平台 | 应用版本 | 构建号 | 安装包 | SHA-256 |
| --- | --- | ---: | --- | --- |
| Android 手机版 | 0.20.0 | 40 | `entryway-release-0.20.0.apk` | `75fa9e64c7a3dedcfba5c4d2d32c1f348f67dec56cfc78163d10ba063b7a30b6` |
| Android TV 版 | 0.18.0 | 38 | `Entryway-tv-release-0.18.0.apk` | `97e6cd547d935a3383653ab35fc3e7d79ad004fcc7a6a105150972a769b4b327` |
| Windows x64 | 0.18.0 | 37 | `Entryway_0.18.0+37_Windows_x64_Setup.exe` | `b744a11a186350461dc6b4143df1fd5ee833bcc0ae1df6bff4339e1824333477` |

## 跨端改进

- 多弹幕 API 支持在 Android 和 Windows 端并行获取、来源切换和后台加载；TV 端同步完善弹幕菜单与设置。
- Android 播放器控制布局、弹幕热力图、字幕/弹幕交互层、投屏路径和倍速传递功能升级。
- Android TV 增强弹幕缓存、继续观看去重、媒体库缓存和黑色主题可读性。

## Android 手机版 0.20.0

- 播放器控制面板重新布局，辅助按钮缩小并减少误触，进度条加入弹幕热力图。
- 支持多弹幕 API 并行请求、来源切换、Google Cast、DLNA 和局域网中继投屏。
- 新增“倍速播放传递”设置，切换下一集时可沿用当前倍速。
- 使用 Android Debug 证书签名；`v0.19.0` 正式证书包仍需先卸载。

## Android TV 版 0.18.0

- 完善多来源弹幕设置、加载缓存和播放器菜单交互。
- 继续观看去重、媒体库缓存、数量显示和异常服务器隔离逻辑同步改进。
- 优化黑色主题下弹窗文字、遥控焦点和弹幕显示可读性。

## Windows x64 0.18.0+37

- 支持多个弹幕 API 来源、轨道管理和手动匹配。
- 弹幕搜索后台执行，视频优先进入播放/缓冲流程，服务端剧集按剧名和集号自动匹配。
- 安装包未进行代码签名，SmartScreen 可能显示未知发布者提示。
- Windows 安装包构建于 `f35a0e384b5619008aa25c1acbff1fcd31656ce7`；该提交与发布候选 `290e56c` 的 Windows 文件一致。

## 兼容性

- Android 手机和 TV：Android 8.1（API 27）及以上。
- Windows：Windows 10 或更高版本，x64。
- Android 安装包使用项目 1.0 前的 Debug 证书签名，Windows 安装包未签名。

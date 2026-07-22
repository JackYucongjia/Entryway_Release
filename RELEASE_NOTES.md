# Entryway Mobile 0.18.0 / TV 0.16.1 / Windows 0.15.0+34

本次批次为 Android 手机、Android TV 与 Windows 三端同批发布。各端应用版本不同，全局标签 `v0.18.0` 仅为本批次 ID。Android 为 1.0 前的 debug 构建。

## 版本与校验

| 平台 | 应用版本 | 构建号 | 文件名 | SHA-256 |
| --- | --- | --- | --- | --- |
| Android Mobile | 0.18.0 | 37 | entryway-debug-0.18.0.apk | `0157c126c61d79767952ed995414eb5d8a1239bb2013a2406996468356c7b820` |
| Android TV | 0.16.1 | 36 | Entryway-tv-debug-0.16.1.apk | `09d2a29d65f37cfc62c85b4fb0a7ce9a8386fac9712fb4653b0cec2f7ad69e9f` |
| Windows x64 | 0.15.0 | 34 | Entryway_0.15.0+34_Windows_x64_Setup.exe | `e9e45536fe981d117f8f261fe82a4e1fbd5b01a1ff515dfdc110253b8992f21b` |

> Android 为 debug 构建（1.0 前约定），Windows 安装包未签名；首次运行可能触发系统安全提示，需手动确认。

## Android Mobile 0.18.0

- 详情页多版本影片可选择要播放的版本，选择贯穿播放全链路（Emby / Jellyfin 均生效）。
- 音轨/字幕弹窗内可按文件调节音频延迟和字幕延迟，按媒体项持久化。
- 带样式 ASS 字幕在 ExoPlayer 下提示样式降级，并提供「覆盖字幕自带样式」开关；PGS/VOBSUB 图形字幕单独提示。
- 完整简体中文 / 英文本地化；语言切换改用应用自有存储，切换即时生效。
- 修复登录页浅色模式文字不可见；修复字幕样式设置需重开播放器才生效；去除详情页海报毛玻璃。

## Android TV 0.16.1

- 详情页对含多个版本的影片显示版本切换按钮，所选版本贯穿播放链路。
- 注：本版 TV 多版本选择尚未在电视端真机充分验证。

## Windows 0.15.0

- 首页各分区新增“查看全部”浏览页。
- 更新检测与安装策略完善。

## 已知问题

- 图形字幕（PGS/VOBSUB）在 ExoPlayer 下颜色不可调，属播放器框架限制，可切换 mpv 内核。
- Windows 安装包未签名。

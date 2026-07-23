# Entryway Mobile 0.18.0 / TV 0.16.1 / Windows 0.16.0+35

本批次仅 Windows 端有代码更新，Android 手机版和 TV 版沿用 v0.18.0 已验证安装包。Android 为 1.0 前的 debug 构建。

## 版本与校验

| 平台 | 应用版本 | 构建号 | 文件名 | SHA-256 |
| --- | --- | --- | --- | --- |
| Android Mobile | 0.18.0 | 37 | entryway-debug-0.18.0.apk | `0157c126c61d79767952ed995414eb5d8a1239bb2013a2406996468356c7b820` |
| Android TV | 0.16.1 | 36 | Entryway-tv-debug-0.16.1.apk | `09d2a29d65f37cfc62c85b4fb0a7ce9a8386fac9712fb4653b0cec2f7ad69e9f` |
| Windows x64 | 0.16.0 | 35 | Entryway_0.16.0+35_Windows_x64_Setup.exe | `4f4652d5773b383291e0469c2e5a03f03cc0b25a707ebe34b02653fd958f3a14` |

> Android 为 debug 构建（1.0 前约定），Windows 安装包未签名；首次运行可能触发系统安全提示，需手动确认。

## Android Mobile 0.18.0

本批次无变化，沿用 v0.18.0 的 0.18.0。

## Android TV 0.16.1

本批次无变化，沿用 v0.18.0 的 0.16.1。

## Windows 0.16.0

- 首页所有横向媒体行新增浮动左右滚动箭头，鼠标悬停时显示，点击可平滑横向浏览。
- "继续观看"和"我的媒体"分区新增"查看全部"入口。
- "我的媒体"查看全部改为库目录选择页，先选库再看内容。
- 子媒体库行最大条目数从 12 提升至 24，最大化窗口时可展示更多内容。
- 修复离线下载页面进入后无法退出的问题（新增返回按钮）。

## 已知问题

- 图形字幕（PGS/VOBSUB）在 ExoPlayer 下颜色不可调，属播放器框架限制，可切换 mpv 内核。
- Windows 安装包未签名。

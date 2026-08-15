# Entryway v0.24.0

本批次将 Android 手机版公开持续发布切换到 **Preview** 构建，并集中发布界面流畅度、隐私服务器保护、缓存搜索、Dolby Vision 与 mpv 稳定性等更新。Android TV 和 Windows 本批次没有代码变化，继续复用上一版已验证安装包。

> Preview 是 release 形态的非 debuggable 构建，启用 R8、AOT 与 Baseline Profile，但仍使用历次公开 Debug 包相同的调试证书，现有用户可直接覆盖安装。它属于公开持续发布渠道，不是正式 Release 构建。

## 版本信息

| 平台 | 应用版本 | 构建号 | 渠道 | 安装包 | SHA-256 |
| --- | --- | ---: | --- | --- | --- |
| Android 手机版 | 0.24.0 | 45 | Preview | `entryway-preview-0.24.0.apk` | `413dc569c88b3bff6140609d584d3b826a536f85f2c40ddda57008c839c47ae0` |
| Android TV 版 | 0.18.1 | 39 | Debug | `Entryway-tv-debug-0.18.1.apk`（沿用 `v0.23.0`） | `f9a7ef9f71a92df4c0469e75c1e36863062631a9735da417b7b237d54b97e4ba` |
| Windows x64 | 0.18.0 | 37 | Debug | `Entryway_0.18.0+37_Windows_x64_Setup.exe`（沿用 `v0.23.0`） | `b744a11a186350461dc6b4143df1fd5ee833bcc0ae1df6bff4339e1824333477` |

## Android 手机版 0.24.0

### Preview 构建与界面性能

- 公开持续发布从 Debug 切换到 Preview：关闭调试模式并启用 R8、AOT 与 Baseline Profile，减少 Debug 构建对启动和界面性能的限制。
- 首页滚动视差、图片阴影与播放器进度更新改为更轻量的绘制和局部状态更新，避免整页或整层控件逐帧重组。
- 首页数据由高频主线程轮询改为数据就绪后主动推送。
- 页面切换统一为约 300 毫秒的方向性转场，精简重复淡入、缩放和多组按压弹簧动画。
- 完善手机、Medium 平板与 Expanded 平板的布局规范。

### 搜索与首页缓存

- 搜索页优先从各服务器的 Home Snapshot 缓存立即返回结果，后台实时搜索完成后再替换。
- 慢服务器或暂时异常的服务器不再让搜索页长期空白，实时搜索失败也不会清空已有缓存结果。
- 读取其他服务器缓存时不切换当前活动服务器；首页缓存更新后同步刷新搜索缓存。
- 首页轮播支持直接展示海报，减少横图裁切造成的信息损失。

### 隐私与稳定性

- 私密服务器新增密码与生物识别保护，并确保进入隐私设置前也需要完成验证。
- 修复系统备份排除规则未覆盖 DataStore，导致登录凭据与服务器列表可能被纳入系统云备份的问题。
- 修复通知权限被拒绝或撤销后，下载通知可能导致崩溃的问题。
- 修复详情页重复 artwork tag 可能触发崩溃的问题。
- 修复登录页部分小米设备键盘安全区过大，以及 Logo 四周出现白色边线的问题。
- 修复深色主题下卡片出现不协调青色描边、语言切换后设置项未刷新及服务器标签中文缺失的问题。

### 播放器、Dolby Vision 与 mpv

- 修正 Dolby Vision Profile 5 的色彩与播放路径，根据 Profile、基底层和设备解码能力选择合适策略。
- mpv 对需要修正的 Dolby Vision 内容启用 `gpu-next` 与软件解码，普通内容恢复默认路径；ExoPlayer 使用设备解码器能力判断 Dolby Vision 支持。
- 新增播放器高级配置：音频解码、gpu-next、快速解码、立体声降混、图片字幕拉伸、不受信任证书、mpv 详细日志、时钟、方向、HDR 色彩模式与最高刷新率等。
- 补齐此前只作用于 ExoPlayer 的 mpv 设置，包括 `vd-lavc-dr`、`target-colorspace-hint`、`gpu-api`，并让全屏/最大化画面设置在 mpv 加载完成后正确生效。
- 修复部分 115/云盘 302 直链大体积 MKV 在 mpv 读取尾部索引时遇到 Range 403 后直接 EOF、跳片尾或进入下一集的问题；连接失败后会在实际请求层重建连接。
- 新播放加载动画替换旧实现，并为 Preview/R8 增加 mpv JNI 保留规则。
- 播放进度或播放完成后会刷新首页继续观看等相关区域，同时保留现有缓存策略。

## Android TV 0.18.1

- 本批次无代码变化，沿用 `v0.23.0` 的 Debug APK。

## Windows x64 0.18.0+37

- 本批次无代码变化，沿用 `v0.23.0` 的 Debug 安装包。
- Windows 端正在重构，预计 **2026 年 8 月 17 日**正式发布新版。
- 当前安装包未进行代码签名，SmartScreen 可能显示未知发布者提示。

## 兼容性与构建信息

- Android 手机和 TV：Android 8.1（API 27）及以上。
- Windows：Windows 10 或更高版本，x64。
- 手机版构建命令：`./gradlew :app:assemblePreview`。
- 手机版 Preview 签名证书 SHA-256：`bbd12fc3757222334f11f22a238012a4745a4423ac07b9dd76b3e887691505c6`。
- 源码提交：`f7fdc71bb1134973121118930995f1a7f2895941`。
- 源码标签：`v0.24.0`。
- 自动验证：`:app:assemblePreview`、`:app:testDebugUnitTest`、`:core:testDebugUnitTest`、`:data:testDebugUnitTest` 与官网 65 项 Node 测试均通过。

### 已知项

当前随包 Baseline Profile 主要覆盖冷启动与登录页；已登录后的首页、详情页与播放器基准数据仍需后续在真实服务器环境中继续采集。

---

# Entryway v0.23.0

本批次为 Android 手机版弹幕曲线和全屏显示更新，采用 Debug 持续发布规则；Android TV 和 Windows 无代码变化，沿用已验证安装包。各端应用版本独立维护：Mobile `0.23.0`、TV `0.18.1`、Windows `0.18.0+37`。

> 本批次是持续发布用的 **Debug 版本**，不是正式 Release 版本。正式版将在用户明确确认后单独构建和发布。

## 版本信息

| 平台 | 应用版本 | 构建号 | 安装包 | SHA-256 |
| --- | --- | ---: | --- | --- |
| Android 手机版 | 0.23.0 | 44 | `entryway-debug-0.23.0.apk` | `3348b2b4de53e8bf3d14e5a154ee774cbc7db37cd5a9a57c0cfd8a47f31dd523` |
| Android TV 版 | 0.18.1 | 39 | `Entryway-tv-debug-0.18.1.apk`（沿用 `v0.22.0`） | `f9a7ef9f71a92df4c0469e75c1e36863062631a9735da417b7b237d54b97e4ba` |
| Windows x64 | 0.18.0 | 37 | `Entryway_0.18.0+37_Windows_x64_Setup.exe`（沿用 `v0.22.0`） | `b744a11a186350461dc6b4143df1fd5ee833bcc0ae1df6bff4339e1824333477` |

## Android 手机版 0.23.0

### 弹幕曲线样式

- 弹幕设置新增“弹幕曲线样式”开关。
- 关闭时使用平滑曲线，适合观察整段视频的弹幕密度趋势。
- 开启时使用峰谷曲线，以更细的时间采样和折线表现突出弹幕密集时刻与剧情高潮。

### 全屏弹幕显示

- 修复播放器隐藏控制栏进入全屏后，第一行弹幕被顶部区域遮挡的问题。
- 控制栏显示时继续保留完整避让距离；控制栏隐藏时仅保留必要顶部安全区，减少画面上方空白。

## Android TV 0.18.1

- 本批次无代码变化，沿用 `v0.22.0` 的 Debug 安装包。

## Windows x64 0.18.0+37

- 本批次无代码变化，沿用 `v0.22.0` 的 Debug 安装包。
- 安装包未进行代码签名，SmartScreen 可能显示未知发布者提示。

## 兼容性

- Android 手机和 TV：Android 8.1（API 27）及以上。
- Windows：Windows 10 或更高版本，x64。
- Android 安装包使用项目 1.0 前的 Debug 变体和证书签名，Windows 安装包未签名。

## 构建信息

- 源码提交：`8d6778b42b7a5f351921248d3a3debde99142aad`
- 源码标签：`v0.23.0`
- 自动验证：`:app:assembleDebug`、官网静态页 65 项测试

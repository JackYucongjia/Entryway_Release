# Entryway v0.21.1

本批次仅包含 Android 手机版 Bugfix，采用 Debug 持续发布规则；Android TV 和 Windows 没有代码变更，沿用 `v0.21.0` 已验证安装包。各端应用版本独立维护：Mobile `0.21.1`、TV `0.18.0`、Windows `0.18.0+37`。

> 本批次是持续发布用的 **Debug 版本**，不是正式 Release 版本。正式版将在用户明确确认后单独构建和发布。

## 版本信息

| 平台 | 应用版本 | 构建号 | 安装包 | SHA-256 |
| --- | --- | ---: | --- | --- |
| Android 手机版 | 0.21.1 | 42 | `entryway-debug-0.21.1.apk` | `90dea56a72e1b686858bcb3109d3f22ef6e348be54348290bc40ef2913771418` |
| Android TV 版 | 0.18.0 | 38 | `Entryway-tv-debug-0.18.0.apk`（沿用 `v0.21.0`） | `0f51f2030f558d950262ed143551a91bb30e8f4a877ce0f9eb4632beb0cbca86` |
| Windows x64 | 0.18.0 | 37 | `Entryway_0.18.0+37_Windows_x64_Setup.exe`（沿用 `v0.21.0`） | `b744a11a186350461dc6b4143df1fd5ee833bcc0ae1df6bff4339e1824333477` |

## Android 手机版 0.21.1

- 修复剧集切集时 Hero 和整剧简介被重复刷新的问题。
- 修复分集胶囊与单集卡片的联动滚动定位。
- 压缩版本、音轨、字幕及季选择弹窗的间距与高度。
- 统一弹窗半透明毛玻璃样式，移除双层圆角描边造成的视觉重叠。

## Android TV 版 0.18.0

- 本批次无代码变化，沿用 `v0.21.0` 的 `0.18.0` Debug 安装包。

## Windows x64 0.18.0+37

- 本批次无代码变化，沿用 `v0.21.0` 的 `0.18.0+37` 安装包。

- 安装包未进行代码签名，SmartScreen 可能显示未知发布者提示。

## 兼容性

- Android 手机和 TV：Android 8.1（API 27）及以上。
- Windows：Windows 10 或更高版本，x64。
- Android 安装包使用项目 1.0 前的 Debug 变体和证书签名，Windows 安装包未签名。

## 构建信息

- 源码提交：`35df354d`
- 修复提交：`154f6e45`
- 源码标签：`v0.21.1`

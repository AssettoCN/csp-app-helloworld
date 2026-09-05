# Hello World — App Store 参考/模板应用

x4fab 的原版 CSP Lua 演示应用,由 AssettoCN App Store 分发。它是:

- **上架管线的参考条目**:本仓库就是一个合法 CSP Lua app 的完整形态(manifest + 主脚本 + 资源),用于验证与演示 [csp-appstore-collections](https://github.com/AssettoCN/csp-appstore-collections) 的上架/打包/分发链路
- **开发起步模板**:复制本仓库,改掉 id 与内容,即可作为你自己的 app 起点

## 功能一览(演示了什么)

- **自定义仪表 HUD**:透明窗口绘制速度表(`fullscreenUI` 回调,可在设置中关闭)
- **虚拟后视镜重定向**:`ac.redirectVirtualMirror`
- **多窗口应用**:主窗口 + Extras 窗口 + YouTube 窗口,含设置页(`FLAGS = SETTINGS`)
- **YouTube 播放**(概念验证):内置 `yt-dlp.exe` 解流 —— 这也演示了 app 打包可执行文件与二进制资源的形态
- **3D 绘制回调**(`Draw3D`)与自定义字体加载(`font.ttf`)

## 文件结构

| 文件 | 说明 |
|---|---|
| `manifest.ini` | 应用清单(ABOUT 段:NAME/AUTHOR/VERSION/DESCRIPTION;多窗口声明) |
| `HelloWorld.lua` | **主脚本 —— 文件名必须等于 app id**(本应用 id = `HelloWorld`) |
| `youtube.lua` / `youtube.png` | YouTube 窗口的辅助脚本与图标 |
| `icon.png` | 应用图标(manifest 引用) |
| `font.ttf` / `TallShip-medium.wmv` | 字体与演示视频资源 |
| `yt-dlp.exe` | 演示用可执行文件 |

## 用作模板

1. 复制本仓库,重命名为 `csp-app-<你的id>`(如 `csp-app-track-radar`)
2. 主脚本重命名为 `<你的id>.lua`,修改 `manifest.ini`(NAME/AUTHOR/VERSION/DESCRIPTION)
3. 遵循[命名规范](https://github.com/AssettoCN/csp-appstore-collections/blob/main/CONTRACT.md):app id 用 PascalCase,与仓库名规范化等价
4. 打 tag(如 `v1.0`),到 [csp-appstore-collections](https://github.com/AssettoCN/csp-appstore-collections) 提交上架

> 原作者:x4fab;本仓库为其公开演示应用的 AssettoCN 分发副本。

## 相关

- 上架索引与分发管线:[csp-appstore-collections](https://github.com/AssettoCN/csp-appstore-collections)
- 商店应用本体:[csp-app-appstore](https://github.com/AssettoCN/csp-app-appstore)

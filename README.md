# vre-doc
<https://github.com/vreui/vre-doc>

威惹界面 (vreui) 文档


## 整体架构

威惹 的架构参考 flutter 设计, 但是使用不同的具体技术 (WebRender, rust, WebAssembly).

+ flutter 架构图:

  ![flutter-arch](./doc/img/flutter-arch-1.png)

  来源: <https://docs.flutter.dev/resources/architectural-overview>

类似的, 威惹的分层设计如下:

+ **框架部分** (Framework, rust/wasm)

  vre-ui <https://github.com/vreui/vre-ui>

  + 材料风格 (Material)

  + 组件 (Widgets)

  + 渲染层 (Rendering)

  + 动画 (Animation), 布局 (Layout, Painting), 输入 (Gestures)

  + (Foundation) 桥, 工具

+ **核心引擎** (Engine, rust)

  vre-core <https://github.com/vreui/vre-core>

  + WebRender

  + wasmer

  + 桥

  + 文本布局 (Text Layout)

  + 平台通道 (Platform Channels)

  + 资源加载 (Asset Resolution)

  + 窗口/GL (winit, glutin)

+ **嵌入层** (Embedder, rust)

  具体平台支持


## 支持平台

威惹 计划支持下列平台:

+ 桌面 (GNU/Linux, Windows)

  vre-dt <https://github.com/vreui/vre-dt>

  + 支持的 GNU/Linux 发行版本: Debian, ArchLinux

  + 最低支持的 Windows 版本: Windows 7

+ Android

  vre-apk <https://github.com/vreui/vre-apk>

  + 最低支持版本: Android 8.1

  + 支持的 CPU 架构: arm64-v8a (aarch64)

+ web

  vre-web <https://github.com/vreui/vre-web>

  + 支持的浏览器: Chrome, Firefox


## 框架设计 (vre-ui)

TODO


## 感谢

威惹 参考和使用了下列项目:

+ WebRender
  <https://github.com/servo/webrender>

+ Wasmer
  <https://wasmer.io/>

+ Flutter
  <https://flutter.dev/>

+ glutin
  <https://github.com/rust-windowing/glutin>

+ winit
  <https://github.com/rust-windowing/winit>

+ android-ndk-rs
  <https://github.com/rust-windowing/android-ndk-rs>

+ Rust
  <https://www.rust-lang.org/>

+ vue 3
  <https://vuejs.org/>

+ React
  <https://reactjs.org/>


## LICENSE

[`CC-BY-SA 4.0+`](https://creativecommons.org/licenses/by-sa/4.0/)

本仓库的内容使用 创意共享-署名-相同方式共享 (CC-BY-SA 4.0) 许可证 (LICENSE).
This repository is released under Creative Common (CC-BY-SA 4.0) license.

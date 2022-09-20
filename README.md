# vre-doc
<https://github.com/vreui/vre-doc>

威惹界面 (vreui) 文档


## 设计文档

+ [整体架构](./doc/整体架构.md)

  威惹的架构参考 flutter 设计, 但是使用不同的具体技术 (WebRender, rust, WebAssembly).

+ [框架设计 (vre-ui)](./doc/框架设计.md)

  威惹的框架部分是 vue 3, react, flutter, rust 的风格混合.

+ [进程线程模型 (vre-core)](./doc/进程线程模型.md)

  多进程多窗口模式 (GNU/Linux, Windows), 单进程单窗口模式 (Android).

+ [使用模式 (vre-core)](./doc/使用模式.md)

  编译模式, wasm 加载模式, 配置模式.


## 支持平台

威惹计划支持下列平台:

+ 桌面 (GNU/Linux, Windows)

  vre-dt <https://github.com/vreui/vre-dt>

  + 支持的 GNU/Linux 发行版本: Debian, ArchLinux

  + 最低支持的 Windows 版本: Windows 7 sp1 x64

+ Android

  vre-apk <https://github.com/vreui/vre-apk>

  + 最低支持版本: Android 8.1

  + 支持的 CPU 架构: arm64-v8a (aarch64)

+ web

  vre-web <https://github.com/vreui/vre-web>

  + 支持的浏览器: Chrome, Firefox


## 感谢

威惹参考和使用了下列项目:

+ WebRender
  <https://github.com/servo/webrender>

+ Wasmer
  <https://wasmer.io/>

+ Flutter
  <https://flutter.dev/>

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

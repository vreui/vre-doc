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

----

框架部分 (vre-ui) 和用户代码 (app code) 一起编译为 WebAssembly.
然后由引擎 (vre-core) 的 wasmer (WebAssembly 运行环境) 执行.

框架部分负责组件和 (高级) 渲染 (布局), 最终生成 显示列表 (DisplayList) 数据.
然后发送给引擎的 WebRender 进行 (像素) 渲染并显示.

框架和引擎是松散耦合的关系, 因此可以很容易的把框架部分整个替换掉.

框架部分目前使用 rust 编程语言,
但是任何可以编译成为 WebAssembly 的语言都可能在框架部分使用.
也就是说支持使用多种编程语言编写用户界面.


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

威惹的框架部分是 vue 3, react, flutter, rust 的风格混合.

+ 组件式设计 (vue, react, flutter):

  整个用户界面由若干组件 (组件树) 构成.
  组件很轻量, 因此使用大量小组件 (flutter).

  组件的种类以及布局算法参照 flutter.

+ 组件属性 (react, flutter):

  使用属性 (props) 向下级组件传递数据, 以及回调函数 (闭包).

+ 静态类型 (flutter, rust):

  传递给下级组件的数据类型 (组件属性) 在编译时检查.

+ 环境数据 (vue, flutter):

  给所有下级组件传递数据 (越级传递).
  类似 vue 3 的 `provide()`, `inject()`.

+ 组件是一个函数 (react):

  一个组件是一个简单的函数.

+ 组件函数只调用一次 (vue):

  类似 vue 3 的 setup, 组件函数仅在创建组件时调用一次.

+ 响应式数据 (vue):

  类似 vue 3 的 `ref()`, `compute()`, `watch()`.

  执行过程中自动收集数据依赖关系, 并触发更新.

+ 不使用 JSX (flutter):

  使用编程语言本身的语法来构建组件树 (render).

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

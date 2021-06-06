# Vueのモーダルウィンドウの基本

[mio3ioさんのモーダルサンプル](https://cr-vue.mio3io.com/examples/modal.html)より。

- `<transition name="modal" appear></transition>` はイディオム
- その中で `modal-overly, modal-window, modal-content` を形成するのがスタンダード
  - それぞれのCSSで見栄えは調整する
- `modal-overlay` は背景で、「背景クリックによるモーダルのクローズ」はevent upの仕組みで親コンポーネントに通知することで実現できる
- サンプルでは「名前付きslot？」のような機能も利用されている

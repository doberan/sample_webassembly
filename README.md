# webAssembly実装サンプル

## 概要
最近流行りの（大分昔・・・）WebAssemblyをRustで実装してみた
参考は下記URLです。
https://developer.mozilla.org/ja/docs/WebAssembly/Rust_to_wasm

## 実際の流れ

### npmユーザ登録
'''
$ npm adduser
Username: <NPM_USER_NAME>
Password:
Email: (this IS public) <NPM_USER_MAIL>
'''

### リポジトリをクローン
'''
$ git clone https://github.com/doberan/sample_webassembly.git
'''

### ワーキングディレクトリ移動
'''
$ cd ./sample_webassembly
'''

### webAssemblyビルド用のcargoツールインストール
'''
$ cargo install wasm-pack
'''

### ビルド
'''
$ wasm-pack build --scope <NPM_USER_NAME>
'''

### アウトプットされたディレクトリに移動
'''
$ cd pkg
'''

### npmに公開
'''
$ npm publish --access=public
'''

### Webフロント実装
※下記リポジトリ内package.json, index.jsの@<NPM_USER_NAME>は書き換える必要がある
'''
$ cd ../../
$ git clone https://github.com/doberan/sample_webassembly_alert.git
$ cd ./sample_webassembly_alert
$ npm install
$ npm run serve
'''
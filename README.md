# parcel を使ってみる

<https://parceljs.org/>

## ファイル構成

```
├── README.md
├── css 
│   └── index.scss 開発用のSCSS
├── dist コンパイルしたファイルが出力される場所
├── index.html
└── js
    └── index.js 開発用のJavaScript
```

## インストール

```bash
npm install -g parcel-bundler
npm install -g node-sass
# 以下は必要に応じて
# npmのバージョンが古いとエラーがでたら npm をアップデート
npm update -g npm
```

## 使う

index.html を percel を使ってコンパイルする

### 開発

```bash
parcel index.html
```

ファイルの変更を監視、コンパイルして <http://localhost:1234> で閲覧できるようにしてくれる。 
SCSSは変更から3秒ぐらいで反映（自動リロード）される。

### ビルド

```bash
parcel build index.html
```

```dist/``` にコンパイルされたファイルが出力されます。

## 記述時の注意

### パスについて

JavaScriptやCSSのパスは相対パスで記述する。 
絶対パスで記述すると、使っている端末の ```/``` が参照される。


### SCSSの書き方

どちらでも動きます。

方法1. JavaScript 上に JavaScriptから見た相対パスで import 
```javascript
import "../css/index.scss";
```
方法2. HTML上に記述
```HTML
<link rel="stylesheet" href="css/index.scss">
```

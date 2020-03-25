# このリポジトリはメンテナンスされていません / This repository is OBSOLETE!

実装中に、同じ地域を対象とした同様のWebサイトが運営されていることがわかりましたので開発を停止することにしました。
最新の新型コロナウイルス感染症に関する情報は以下のサイトからご覧ください。

- 公式: [新型コロナウイルス感染症に関する情報(岩手県)](https://www.pref.iwate.jp/kurashikankyou/iryou/kenkou/jouhou/1026260.html)
- 非公式: [岩手県 非公式 コロナウイルス感染症対策サイト](https://covid19-iwate.netlify.com/)

# 岩手県 新型コロナウイルス感染症対策サイト

東京都による[新型コロナウイルス感染症対策サイト](https://stopcovid19.metro.tokyo.lg.jp/)の岩手県版です。

岩手県立大学ソフトウェア情報学部卒業生有志によって開設され、岩手にゆかりのある有志によって運営されています。

![](https://github.com/iwate-pu/covid19/workflows/production%20deploy/badge.svg)

### 日本語

## 貢献の仕方
Issues にあるいろいろな修正にご協力いただけると嬉しいです。

詳しくは[貢献の仕方](./CONTRIBUTING.md)を御覧ください。


## 行動原則
詳しくは[サイト構築にあたっての行動原則](./CODE_OF_CONDUCT.md)を御覧ください。

## ライセンス
本ソフトウェアは、[MITライセンス](./LICENSE.txt)の元提供されています。

## このサイトから派生したサイト

[Link先](./FORKED_SITES.md)を御覧ください。

## 翻訳者向け情報

翻訳をお手伝いいただける方は、[こちらのドキュメント](./TRANSLATION.md)を御覧ください。

## 開発者向け情報

### 環境構築の手順

- 必要となるNode.jsのバージョン: 10.19.0以上

**yarn を使う場合**
```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev
```

**docker compose を使う場合**
```bash
# serve with hot reload at localhost:3000
$ docker-compose up --build
```

**Vagrant を使う場合**
```bash
# serve with hot reload at localhost:3000
$ vagrant up
```

### `Cannot find module ****` と怒られた時

**yarn を使う場合**
```bash
$ yarn install
```

**docker compose を使う場合**
```bash
$ docker-compose run --rm app yarn install
```

### VSCode + Remote Containersで開発する場合

1. VSCodeの拡張機能「[Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)」を導入します。
2. [この画像（外部サイト）](https://code.visualstudio.com/docs/remote/containers#_quick-start-try-a-dev-container)のように左下部の「Open Folder in Container」でこのリポジトリのルートを選択すれば環境構築が始まります。

#### Topic
- 設定を変更したい場合は、`.devcontainer/devcontainer.json`を修正してください。
詳細は[devcontainer.jsonのリファレンス](https://code.visualstudio.com/docs/remote/containers#_devcontainerjson-reference)を参照してください。
- Remote Container実行時のみ有効な拡張機能「ESLint」を導入していますが、必要に応じて`devcontainer.json`の`extensions`に追加してください。
詳細な手順は[こちら（外部サイト）](https://code.visualstudio.com/docs/remote/containers#_managing-extensions)を参照してください。
- 開発環境を再構築する場合は、左下部の「Rebuild Container」を実行してください。

### 本番環境/その他の判定

`process.env.GENERATE_ENV` の値が、本番の場合は`'production'`に、それ以外の場合は `'development'` になっています。
テスト環境のみで実行したい処理がある場合はこちらの値をご利用ください。

### ステージング・本番環境への反映

`master` ブランチがアップデートされると、自動的に本番サイト https://covid19.iwate-pu.net/ が更新されます。

`development` ブランチがアップデートされると、自動的に開発用サイト https://development--adoring-heisenberg-10359e.netlify.com/ が更新されます。

### ブランチルール

development 以外は Pull Request は禁止です。
Pull Request を送る際の branch は、以下のネーミングルールでお願いします。
（当面はissue番号なしのPRも受け付けます / またPR時に表示されるテンプレート内容も無視してもかまいません）

機能追加系： feature/#{ISSUE_ID}-#{branch_title_name}
ホットフィックス系: hotfix/#{ISSUE_ID}-#{branch_title_name}

#### 基本的なブランチ
| 目的 | ブランチ | 確認URL | 備考 |
| ---- | -------- | ---- | ---- |
| 開発 | development | https://development--adoring-heisenberg-10359e.netlify.com/ | base branch。基本はこちらに Pull Requestを送ってください |
| 本番 | master | https://covid19.iwate-pu.net/  | 管理者以外の Pull Request は禁止です |

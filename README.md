# building-a-static-website-using-gatsby-and-strapi

---

## Strapi のセットアップ

```sh
$ cd ~/Documents/GitHub/building-a-static-website-using-gatsby-and-strapi
$ mkdir tutorial && cd tutorial

$ npx create-strapi-app cms --quickstart
```

http://localhost:1337/admin/ にアクセスして管理者ユーザーを作成する。

`ボードにようこそ!` と表示されたら完了。

Ctrl+C で終了させた後に再度起動したい場合は以下のコマンドを実行する。

```sh
cd ~/Documents/GitHub/building-a-static-website-using-gatsby-and-strapi/tutorial/cms/ && npm run develop
```

ユーザーを追加して、Role に Authenticated を指定する。

article コンテンツタイプを作成し、以下の列を用意する。その後、Entry（記事） を Insert しておく

- title （text ＞ short text）
- content （Rich Text）
- image （media ＞ Single Media）
- author （relation ＞ 多対一）

Article と User の find 権限を有効化する。

## Gatsby のセットアップ

```sh
$ npm install --global gatsby-cli

$ cd /path/to/....../tutorial
$ gatsby new blog
$ cd blog
$ gatsby develop
```

http://localhost:8000 にアクセスして、おじさんの画像が表示されたら完了。

プラグインをインストールするために以下のコマンドを実行する。

```sh
$ cd /path/to/....../tutorial/blog
$ npm install --save gatsby-source-strapi
```

`gatsby-config.js` に追記する。

Index ページ（ `blog/src/pages/index.js` ）を修正する。

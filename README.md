# README

## セットアップ

サイト作成

```shell
hugo new site hugo-newsroom
```

レポジトリ初期化

```shell
cd hugo-newsroom
git init
echo '*~' >> .gitignore
echo '*.bak' >> .gitignore
echo '*.orig' >> .gitignore
echo '.env' >> .gitignore
echo 'public' >> .gitignor
echo 'resources' >> .gitignor
```

テーマ設定

```shell
cd themes
git submodule add git@github.com:onweru/newsroom.git
```

サイト設定

```shell
cd ..
cp -pr themes/newsroom/exampleSite/{content,data,config.toml} .
```

config.toml

```toml
baseURL = "https://higebobo.github.io/hugo-newsroom"
languageCode = "ja"
title = "Hugo Newsroom"
theme = "newsroom"
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

起動確認(http://localhost:1313)

```shell
cp /path/to/someplace/Makefile .
make run
```

Githubレポジトリ作成後

```shell
git remote add origin git@github.com:higebobo/hugo-newsroom.git
git add .
git commit -m 'init'
git push -u origin master
```

## Github Actionsの利用

* .github/workflows/gh-pages.yamlを作成
    * ソースはmasterブランチ
    * 出力はpublicフォルダの内容をgh-pagesブランチ

```shell
make deploy
```

* Github>Settings>Gighub Pages>Source>gh-pages branchに設定する
* しばらく時間がかかる

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:higebobo/hugo-newsroom.git higebobo-newsroom
cd higebobo-newsroom
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new post/hello.md
content/post/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

## Link

* [Newsroom \| Hugo Themes](https://themes.gohugo.io/newsroom/)

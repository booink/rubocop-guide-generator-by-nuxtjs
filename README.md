# rubocop_guide

> RuboCopガイドをNuxt.jsで構築するためのリポジトリです

## Build History

### インストールからサーバー起動まで
新規Nuxt.jsのプロジェクトを生成

``` bash
create-nuxt-app rubocop_guide
> Generating Nuxt.js project in /Users/booink/work/rubocop_guide
? Project name rubocop_guide
? Project description RuboCopガイドをNuxt.jsで構築するためのリポジトリです
? Use a custom server framework (Use arrow keys)
❯ none
  express
  koa
  adonis
  hapi
  feathers
  micro
? Use a custom UI framework
  none
  bootstrap
  vuetify
  bulma
  tailwind
  element-ui
❯ buefy
? Choose rendering mode (Use arrow keys)
❯ Universal
  Single Page App
? Use axios module
  no
❯ yes
? Use eslint
  no
❯ yes
? Use prettier
  no
❯ yes
? Author name Booink
? Choose a package manager
  npm
❯ yarn
```

プロジェクトルートに移動

``` bash
cd rubocop_guide/
```

Markdownで記事を書くためのプラグインをインストール

``` bash
yarn add @nuxtjs/markdownit
```

markdownitを有効にするため、nuxt.config.js の以下の部分を追加
```javascript
   modules: [
     // Doc: https://github.com/nuxt-community/axios-module#usage
     '@nuxtjs/axios',
     // Doc: https://buefy.github.io/#/documentation
     'nuxt-buefy',
+    '@nuxtjs/markdownit'
   ],
 ```

BulmaのCSSを利用するためにsass-loaderをインストール

``` bash
yarn add sass-loader node-sass
```

サーバーを起動

``` bash
yarn run dev
```

## 静的ファイルに変換してデプロイまで

package.jsonを書き換える

``` javascript
   "scripts": {
     "dev": "nuxt",
     "build": "nuxt build",
     "start": "nuxt start",
-    "generate": "nuxt generate",
+    "generate": "nuxt generate && rm -rf gh-pages/* && cp -r dist/ gh-pages/",
     "lint": "eslint --ext .js,.vue --ignore-path .gitignore .",
     "precommit": "npm run lint"
   },

```

gh-pagesに静的ファイルを吐き出す

``` bash
yarn generate
```

静的ファイルディレクトリに移動

``` bash
cd gh-pages/
```

gitの初期設定

``` bash
git init
git config --local user.email "booink.work@gmail.com"
git config --local user.name "booink"
git remote add origin https://github.com/booink/rubocop-guide.git
```

ファイルをコミットして、pushすると自動的にデプロイされる

``` bash
git checkout -b gh-pages
git add .
git commit -m "Lint/UriEscapeUnescape"
git push -u origin gh-pages
```

[完成](https://booink.github.io/rubocop-guide/)

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).

# nextjs13-template

## 概要

- 新規プロジェクトの際にクローンするなどして利用するもの
- 開発プロジェクトの自由度を縛らない程度のものしか導入していないつもりです
- フォーマッター等（eslint と prettier）導入済み
  - prettierrc や eslintrc は各自でプロジェクトごとに改変してください
- ディレクトリ構成はある程度整えてある

## 始め方

- ターミナルを開いてプロジェクトのルートディレクトリで以下実行

  ```
    //  各種必要なパッケージの導入
    yarn install
    //  開発サーバー起動、localhost:3000で見れるはず
    yarn dev
  ```

- ファイル保存時に整形ツールが自動で整形できるように、以下のエディタの拡張機能をインストールする
  - https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
  - https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode

## 導入ライブラリについて

### ESLint

- JavaScript や TypeScript の静的解析ツール
- 構文エラーとかあれば書いてる途中で教えてくれる
- `/.eslintrc.json`を編集することで独自ルールを設けることもできる
  - 変数はキャメルケースで定義しなければならない
  - boolean の変数は接頭辞として`is`が付いていなければいけない
  - など
- https://eslint.org/

### Prettier

- 整形ツール、さまざまな言語に対応している
  - JavaScript
  - TypeScript
  - HTML
  - CSS
  - Sass
  - JSON
  - Markdown
  - YAML
- `/.prettierrc`を編集することで整形ルールを儲けて、その通りに自動で整形させることができる
  - シングルクォートをダブルクォートに置換する
  - 120 文字で折り返す
  - など
- https://prettier.io/

## ディレクトリ構成

- /
  - /.next : ビルドしたファイルの置き場（自動生成のため、手動で更新しないこと）
  - /out : ビルド内容をもとに吐き出される静的ファイルの置き場（自動生成のため、手動で更新しないこと）
  - /public : 写真などの素材置き場、img タグの src プロパティから`/public/hoge.png`を参照するときは`<img src="/hoge.png" />`でアクセスできる
  - /src : 開発者が触るソースコードをまとめる場所
    - /components : ユーザー定義のコンポーネント群
      - SomeComponent.tsx : コンポーネントの中身
      - index.ts : コンポーネント群のエントリーポイント(バレル)
    - /pages : page 群
    - /styles : page のスタイルシート群
  - .eslintignore : eslint の対象から除外するファイルを明記するファイル
  - .eslintrc.json : eslint が解析するルールを書くファイル
  - .prettierrc : prettier が整形するルールを書くファイル
  - next-config.json : Next.js のカスタムする設定を書くファイル
  - tsconfig.json : TypeScript に関する設定を書くファイル

## 元ネタ
NestJS REST API 開発 チュートリアル集
https://zenn.dev/mikakane/books/nestjs-tutorial

## 作業メモ
### 2024/1/29
- 02 2-2. NestJSの環境構築 / NestJS の環境構築
  ```
  npx nest new my-nest-sample
  ```
  について、パッケージ名（@nestjs/cli）と実行コマンド（nest）が異なることからか
  ```
  npx --package @nestjs/cli nest new my-nestjs-app
  ```
  でないと実行不可

- 上記実行時、利用するnpmパッケージマネージャを選択させられるがnpm推奨
- yarn（現時点: v4.0.2）だとprisma関連のパッケージ（v5.8.1）が解決できず、「03 2-3. データベースとの接続」の「prisma generate」で詰む（恐らくyarn v4系とprisma v5系の相性の問題）

- 03 2-3. データベースとの接続
  this.$on('beforeExit') prisma v5以降下記は動作しない
  ```
  this.$on('beforeExit')
  ```
  ので
  ```
  process.on('beforeExit')
  ```
  に書き換え

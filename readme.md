# 設計レビュー最終課題README
## やること
- 以下のレビュー対象の設計書について、レビューを行ってもらいます。
- **修了試験は2段階に分かれています。**
  - 1段階は**問題抽出**。
    - 対象の設計書について、添付している**markdownファイル**に、問題点を列挙してください。
    - 形式は、テンプレートの形を守ってください。
   - 2段階は**レビュー文章化**。
      - **問題抽出に合格してから取り組んでください。**
      - 1段階で提出した問題点について、要件に従う形にしてもらえるようレビュー文章を作成してください。
      - 形式は課題に対して、引用する書き方にしてください。

### レビュー形式例
```
## エンドユーザ
- 論理削除を考慮していない。（問題点）
  > ユーザを削除した場合、該当のレコードはどうなりますか？（レビュー）
```

## 準備(リポジトリのfork)
- このリポジトリをforkし、自分のアカウントで使うリポジトリを作成してください。

## 提出方法
- 設計図に対する問題点/レビューを該当するmarkdownファイルに記載してください。
- 問題抽出では、**１つの設計書を問題抽出するごと**に提出してください。
- レビュー文章化では、**全ての設計書をまとめて**提出してください。
- branchは**master**で行ってください。
- commit messageは`問題抽出_xxx_n回目`, `レビュー_n回目`としてください。
    - xxxは設計書の種類。
- 提出するときはfork先のリポジトリURLを[フォーム](https://forms.gle/DXSfWbYKxQH3hegG9)から提出してください。

## 研修担当からのレビュー
- 提出してもらったGithubリポジトリに対して、Pull Requestとしてレビューが飛んできます。
- **合格するまで**は、そのレビューを踏まえて修正を行い、再度[フォーム](https://forms.gle/DXSfWbYKxQH3hegG9)から提出をお願いします。

## レビュー対象の設計書
### データベース設計
- ER図
  - 01 : https://drive.google.com/open?id=1vmMD2q76GOOmyuhuzgkJsk9nRcNhoOhE
  - 02 : https://drive.google.com/open?id=1iYVDuKeXzSM7Cq7bpXXR_SNu_qqxmdx0
- テーブル定義書
  - 01 : https://drive.google.com/open?id=1wZb6VJ-R-l7HDswsxH76Y3_ZXx07vZUyJ4wwFFI2Svk
  - 02 : https://drive.google.com/open?id=1jx9q22FS50O2qUz0miKJvt-gflGKFfcrrZ9Ubu_z9_g
  
### アプリケーション詳細設計
- 設計書 : https://drive.google.com/open?id=1EWayigGHKoqL_wm6fKodic7vaE5BXuxsSa5LM8GOUQc
- 参考ワイヤーフレーム : https://drive.google.com/open?id=1Zurk2OCDyitQuVNZcFHkeaxf-RXEdYrf

# 設計書必須要件
以下は、必須要件になります。少なくとも以下の要件が満たされていることを確認しましょう。

## アプリケーション概要
このアプリケーションは、CDのECサイトです。

## データ要件
### 管理者
- メールアドレスとパスワードだけもつ

### ユーザ
- 登録時のデータは次の通り
	- 実名
	- 現住所(郵便番号含む)
	- 電話番号
	- メールアドレス
	- パスワード
- 現住所とは別に複数の配送先データをもつ
- 退会状態を管理する

### 配送先
- 宛名
- 郵便番号
- 住所

### 商品
- 商品名
- 税抜価格
- 発売日
- ジャケット画像(一つだけ)
- ディスク枚数
- ディスクに対応して曲を管理できる
- 販売ステータス
	- 販売中, 販売中止
- 商品ごとに、アーティスト・レーベル・ジャンルを一つずつ設定できる。

### 商品在庫関係
- 在庫数は入荷記録と受注詳細記録から算出する
- 入荷は、どの商品をいくつ入荷するか記録する。
- 受注詳細は、どの商品がいくつ、いくらで購入したか記録する

### 購入
- 複数の商品を指定した数で購入するためのカートデータをもつ
- 購入記録は次のデータを持つ
	- 購入者
	- 購入商品
	- 購入価格
	- 配送先
	- 送料
	- 配送ステータス
	- 購入方法(銀行振込、代引き、クレジットカード)

## 画面必須要件
### エンドユーザ
- 登録
- ログイン
- 商品一覧
- 商品詳細
- カート一覧
- 購入情報入力画面(配送先、購入方法)
- 購入確認画面
- 購入完了画面
- マイページ(ユーザ情報、購入履歴)

### 管理者
- ログイン
- 商品一覧
- 商品詳細
- 商品登録
- 商品編集
- 商品入荷
- 受注一覧
- 受注詳細
- ユーザ一覧
- ユーザ詳細
- ユーザ編集
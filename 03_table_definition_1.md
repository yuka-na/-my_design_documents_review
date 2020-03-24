# テーブル定義書1
## 全体
- PKにカラム名をつける必要はない (「admin_id」→ 「id」)
- テーブル名は小文字スタート
- ユーザ登録日時、ユーザ更新日時ではなく単に[登録日時],[更新日時]で良い

## Admin
- PK、AUTO INCREMENT、INDEXにまるが入っていない
- メールアドレス、パスワードにadminはいらない

## Users
- 郵便番号はstring型にする
- 電話番号はstring型にする
- メールアドレス、パスワードにuserはいらない
- 退会ステータスはboolean型にする

## Products
- disc_idがいらない
- ジャンルID、レーベルID、アーティストIDのFKにまるが入っていない
- cd_image,cd_titleのcd_がいらない
- 在庫数がいらない
- deleted_atカラムを追加する

## Discs
- FKはproduct_id(単数形)にする
- トラックNo.がいらない
- ティスクNo.をつくる

## Songs
- PKがない
- 曲名のテータ型はstringにする
- トラックNo.をつくる

## Labels
- PKがない
- FKはproduct_id(単数形)にする
- レーベルではなく[レーベル名]にする、カラム名も[label_name]みたいな感じにする

## Artists
- PKがない
- FKはproduct_id(単数形)にする
- artistではなく[artist_name]にする
- artistのデータ型がintegerになっている

## Genre
- PKがない
- FKはproduct_id(単数形)にする
- genreではなく[genre_name]にする
- genreのデータ型がintegerになっている

## Cart_item
- PKがない
- FKはproduct_id(単数形)にする、データ型がない
- buy numではなく[buy_num]にする
- 小計金額はいらない

## Buy_details
- カラム名を[受注]など管理者視点のものにする
- buy numではなく[buy_num]にする
- 小計金額はいらない
- BuyテーブルのFKが必要


## Buy
- 購入詳細IDはいらない
- 郵便番号、宛名のカラムがない
- 購入日はいらない


# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

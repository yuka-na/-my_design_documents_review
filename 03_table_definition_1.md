# テーブル定義書1
## 全体
- PKにカラム名の接頭語をつける必要はない (「admin_id」→ 「id」など)
- テーブル名は小文字スタート
- ユーザ登録日時、ユーザ更新日時ではなく単に[登録日時],[更新日時]で良い

## Admin
- PK、AUTO INCREMENT、INDEXにまるが入っていない
- メールアドレス、パスワードにadminはいらない
- テーブル名は複数形

## Users
- 郵便番号はstring型にする
- 電話番号はstring型にする
- メールアドレス、パスワード、名前にuserはいらない
- 退会ステータスはboolean型にする
- l_name,f_nameのような略語を使用しない
- 配送先住所は必要ない
  > 配送先テーブルを新たにつくる
- menber_statusではなく[is_active]みたいな命名にする

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
- songではなく[name]にする

## Labels
- PKがない
- FKはproduct_id(単数形)にする
- レーベルではなく[レーベル名]にする、カラム名も[name]みたいな感じにする

## Artists
- PKがない
- FKはproduct_id(単数形)にする
- artistではなく[name]にする
- artistのデータ型がintegerになっている

## Genre
- PKがない
- products_idは必要ない
- genreではなく[name]にする
- genreのデータ型がintegerになっている
- テーブル名は複数形

## Cart_item
- PKがない
- FKはproduct_id(単数形)にする、データ型がない
- buy numではなく[buy_num]にする
- 小計金額はいらない
- テーブル名は複数形

## Buy_details
- カラム名を[受注]など管理者視点のものにする、テーブル名も[order_details]に
- buy numではなく[buy_num]にする
- 小計金額はいらない
- BuyテーブルのFKが必要



## Buy
- 購入詳細IDはいらない
- 郵便番号、宛名のカラムがない
- 購入日はいらない
- テーブル名は複数形
- テーブル名を[orders]にする
- payカラムではなく[payment_way]などわかりやすい命名にする
- stockではなく[total_price]などにする
- 支払い方法はinteger型にしenumなどを使用する


# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

<font color="Red">再提出の際はこのレビューを残しておいてください。</font>


## Users
- 住所とは別の配送先住所があることに対して、何か問題はございませんか。
 - 配送先の住所の個数に注目して考えてみてください！
- member_statusカラムはどんな働きをするカラムかイメージしやすいでしょうか
 - このままではなんのステータスかが曖昧です。

# テーブル定義書1
## 全体
- テーブルのPKがidだけでOK、わざわざテーブル名_idとしなくてもいい
- テーブル名の最初の文字は小文字で始める
- テーブルのPKが無いものは追記する
- テーブル名に半角スペースがあるものは_でつなぐ

## Admin
- AUTO INCREMENtとINDEXにチェックがない
- メールアドレスとパスワードにadmin_はいらない

## users
- user_l_nameはカラムの名前として分かりづらいので避けたほうがいい
- user_tel、user_email、user_passwordはusersのテーブルというのがわかっているので、わざわざuserと書く必要はない

## products
- ディスクIDは必要ない
- ジャンルID、レーベルID、アーティストIDのFKにチェックが付いていない
- 商品登録時では在庫数がいくつかは分からないため、在庫数のnot:nullは外す

## discs
- ディスクIDにINDEXが付いていない

## songs
- songカラムは曲名なのでstring

## labels
- 商品IDは必要ない

## artists
- アーティスト名は文字列なのでstring
- 商品IDは必要ない

## genres
- ジャンル名は文字列なのでstring
- 商品IDは必要ない

## cart_items
- 商品IDのデータ型が書かれていない
- buy numの間は＿でつなぐ

## buy_datails
- product_idが無い
- buy_idが無い

## buys
- buy_details_Idが必要ない

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

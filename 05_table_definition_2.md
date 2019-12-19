# テーブル定義書2
## 全体
- 各テーブルのPKは〇〇_idではなく、idのみでOK

## adimins
- admin_idにINDEXがない
- admin_email,admin_passwordのadminの部分は分かりきっていることなので、不要

## users
- 退会ステータスのデータ型に記述されているenumはデータ型ではないので、データ型はintegerのみでOK
- user_l_nameのlastを省略しない。user_f_name、user_l_kana、user_f_kanaも同様に。
- user_l_nameのuserは分かりきっているのでわざわざ書く必要はない
- user_tel, user_email, user_passwordのuserは必要ない

## ships
- ship_idにINDEXがない

## products
- products_idのsはいらない
- stockは在庫数 - 購入数で算出できるので必要ない
- stock_statusはenumなのでdefault:0を入れる

## discs
- disc_idにINDEXがない
- products_idのsはいらない

## songs
- songで曲名のカラムを表すのは分かりづらいので、nameなどにする

## labels
- labelでレーベル名を表すのは分かりづらいので、nameなどにする

## artists
- artistでアーティスト名を表すのは分かりづらいので、nameなどにする

## genres
- genreでジャンル名を表すのは分かりづらいので、nameなどにする

## cart_items
- テーブル名を_でつなぐ(cart_itemsなどとする)
- カートアイテムIDはcart_item_idとする（最初を大文字にしない、_でつなぐ）
- カートアイテムIDにINDEXがない
- products_idのsはいらない
- buy numはbuy_numとして間は＿でつなぐ

## sell_details
- sell_details_Idはsell_detail_idとする（単数形にする・idは小文字）
- products_idのsはいらない
- productsから見たら子モデルなので、product_idがFKになる
- sellsから見たら子モデルなので、sell_idがFKとして必要
- 購入時の金額を記録しておくカラムがありません
- 

## sells
- テーブル名が購入は分かりづらいので、管理者側から見たら受注の内容なので、そのような名前にする
- sell_idにINDEXがない
- そもそもsell_detail_idがいらない(sellsが親、selldetailsが子なので)
- ship_address,ship_tel,ship_code,ship_name,ship_costはそれぞれshipは分かっているので必要ない


# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

**研修担当レビュー**
合格です！
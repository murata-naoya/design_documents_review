# テーブル定義書2 レビュー文章化
## 全体
- それぞれのテーブルのプライマリーキー(id)ですが、〇〇_idとなっているのをidに統一した方がわかりやすいです。

## adimins
- admin_idにINDEXがない
- admin_email,admin_passwordのadminの部分は分かりきっていることなので、必要ありません。

## users
- 退会ステータスのデータ型に記載されているenumですが、rubyにおいてはデータ型ではありません。integer型のデータをenum形式で使うという流れです。
- user_l_nameのlは何を指しているのでしょうか。省略して書くと何を示しているかが分かりづらいです。user_f_name、user_l_kana、user_f_kanaも同様です。
- user_l_nameのuserは分かりきっているのでわざわざ書く必要はありません。user_tel, user_email, user_passwordも同様です。

## ships
- ship_idにINDEXがありません。

## products
- products_idのsは必要ありません。
- 在庫数は入荷したら手打ちで数値を打ち込むのでしょうか。それではタイプミスが起きやすく、購入された際にも数値の変更をすることが必要になってしまいます。在庫数は入荷数 - 購入数で算出できるので、必要ありません。

## discs
- disc_idにINDEXがない
- products_idのsはいらない

## songs
- songというカラム名で曲名のカラムを表すのは分かりづらいので、nameなどとすると分かりやすいです。

## labels
- labelというカラム名でレーベル名を表すのは分かりづらいので、nnameなどとすると分かりやすいです。

## artists
- artistというカラム名でアーティスト名を表すのは分かりづらいので、nameなどとすると分かりやすいです。

## genres
- genreというカラム名でジャンル名を表すのは分かりづらいので、nameなどとすると分かりやすいです。

## cart_items
- テーブル名の間にスペースがありますが、テーブル名の間にスペースを作ることはできません。テーブル名を_（アンダーバー）でつなぐようにして、cart_itemsなどとしてください。
- PKのカートアイテムIDも上記と同様に、cart_item_idとしましょう。
- 購入枚数カラムも同じで、buy_numとしましょう。
- PKのカートアイテムIDの最初の文字は小文字にしましょう。カラム名は小文字から始まります。
- カートアイテムIDにINDEXがありません。
- products_idのsは必要ないです。

## sell_details
- テーブル名は管理者側から見た時の名前にしましょう。
- PKのカラム名が複数形になってしまっています。複数形にしてください。
- idがIdと最初の文字が大文字になってしまっています。最初は小文字から始まるようにしてください。
- products_idのsは必要ありません。
- FKが何もありませんが、productsから見たら購入詳細は子モデルなので、product_idをFKにする必要があります。
- sellsから見たら子モデルなので、sell_idがFKとして必要です。
- 購入時の金額を記録しておくカラムがありません。このままでは購入後に商品の値段が変更になった場合、購入した履歴の金額も変更されてしまいます。

## sells
- テーブル名は管理者側から見た時の名前にしましょう。
- sell_idにINDEXがありません。
- このテーブル定義書を見てみると、購入詳細が親で購入が子という関係で間違いありませんか。
- ship_address,ship_tel,ship_code,ship_name,ship_costの接頭辞"ship"をカラム名につけてしまうと、データを表示する際にship.ship_addressなどとなり非常に分かりづらいのでshipは必要ありません。

-----------------------------------------------------------------------------------------------------

# テーブル定義書2 問題抽出
## 全体
- 各テーブルのPKは〇〇_idではなく、idのみでOK

## adimins
- admin_idにINDEXがありません。
- admin_emailの"admin"の部分はデータを取得しようとするとadmin.admin_emailとなり、adminが2度続く形になります。なので、カラムにどのテーブルの中にあるのかを示すような接頭辞は必要ありません。admin_passwordも同様です。

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
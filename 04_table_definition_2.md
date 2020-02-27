# テーブル定義書2
## 全体
- PK（主キー）の命名に「テーブル名_」が付いている。

## admins
- PK（主キー）に INDEX が付与されていない。
- メールアドレスとパスワードのカラムに「admin_」が付いている。

## users
- 「姓」の漢字が間違っている。
- user_l_name、user_f_name、user_l_kana、user_f_kanaカラムの命名が適切でない。
- member_statusカラムが何を表すかが不明。

## ships
- ship_name、ship_address、ship_tel、ship_codeカラムのそれぞれに「ship_」が付いている。

## product
- 在庫数カラムがある。
- 在庫ステータスカラムがある。

## discs
- FK（外部キー）であるproducts_idカラムの命名が適切でない。

## songs
- songカラムは曲名を表すため、命名が適切でない。

## labels
- labelカラムはレーベル名を表すため、命名が適切でない。

## artists
- artistカラムはアーティスト名を表すため、命名が適切でない。

## genres
- genreカラムはジャンル名を表すため、命名が適切でない。

## cart items
- テーブル名がスネークケースになっていない。
- FK（外部キー）であるproducts_idカラムの命名が適切でない。
- buy_numは購入枚数を表すため、命名が適切でない。

## sell_details
- FK（外部キー）であるproducts_idカラムの命名が適切でない。
- sell_numカラムは購入枚数を表すため、命名が適切でない。
- 購入時価格を保持するカラムがない。

## sell
- sellカラムは支払い方法を表すため、命名が適切でない。
- 購入詳細IDカラムがある。

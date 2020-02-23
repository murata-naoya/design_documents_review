# ER図1
## 全体
- テーブルに登録日, 更新日のカラムがない。
- 管理者とエンドユーザー、商品が関連づけられている。
- 受注明細テーブルがない。

## エンドユーザー
- 会員ステータスのカラムがない。
- 配送先を複数保持することが出来ない。

## 商品
- 在庫数カラムが存在している。
- 論理削除の機能が存在しない。
- ディスクに対応して曲を管理できていない。
- 入荷情報を保持できない。
- アーティスト, レーベル, ジャンルそれぞれとのアソシエーションができていない。
- 発売日を保持するカラムがない。

## カート
- カート内商品を保持するため、テーブル名が適切でない。
- 外部キーである商品IDが機能していない。
- エンドユーザーとカートを関連付けていない。
- 合計金額カラムが存在している。
- PKの名前がテーブル名と合致していない。

## 決済
- 受注情報を保持するためテーブル名が適切でない。
- 送料を保持するカラムがない。
- 請求総額を保持するカラムがない。
- 購入日カラムがある。
- 宛名と郵便番号カラムがない。
- カートとのリレーションがある。


# レビュー1回目

## 全体
- 受注明細テーブルがありません

## エンドユーザー
- カート内に商品を追加することが出来ない。
  > なぜそう思いましたか？
  
## 商品
- ステータスが何を意味しているか不明です。（）に意味を書くのではなくカラム名にわかりやすい命名をします。

## カート
- 注文明細（受注明細）を保持するテーブルであるから、テーブル名が適切でない。
  > 注文明細を保持するテーブルではないです。カートアイテムを保存するテーブルであることを前提としてもう一度問題点を探してください。

## 決済
- 決済情報の1レコードに対してステータス（発送状況）は1つであるから購入履歴テーブルとのアソシエーションが適切でない。
  > 1対多のリレーションは間違っていません。ステータスカラムを持たせるテーブルが間違っています。

- テーブル名と機能が異なっています。
- 購入日カラムは必要ありません。
- カートとのリレーションは必要ありません。
- 宛名と郵便番号カラムが必要です。
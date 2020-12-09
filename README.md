# テーブル設計

## users テーブル

| Column              | Type   | Options     |
| ------------------- | ------ | ----------- |
| email               | string | null: false |
| encrypted_password  | string | null: false |
| name                | string | null: false |


### Association

- has_many :books


## books テーブル

| Column      | Type       | Options                        |
| ----------  | ---------- | ------------------------------ |
| title       | string     | null: false                    | 
| publishing  | string     |                                |
| author      | string     |                                |
| user        | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :read


## read テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| comment    | text       |                                |
| star_id    | integer    | null: false                    |
| book       | references | null: false, foreign_key: true |

### Association

- belongs_to :book


### アプリケーション名：月影

## アプリケーション概要
- あなたの本棚をバーチャルに投稿して管理
- 本を買う際、買った本を一覧で見ることができ、持っている本を検索することができる

## url:

## テスト用アカウント
- ID
- password

## 利用方法
1.名前とEメールとパスワードを登録
2.自分の持っている本を写真をとる
3.投稿ページで先ほど撮った写真とタイトル、（作者名、出版社）を登録
4.本の一覧が見られる

## 目指した課題解決
- 漫画を読むことが好きで、たまに本屋に行くと何を買ったか忘れてしまい、記憶だけで買うと家に同じ本があった時悲しいですよね。そんな時、このアプリがあれば大丈夫！自分の本棚にある漫画がどれだったかが一目瞭然！しかも！買った本の評価をすることができ、星の数でその本が面白かったかどうかが一目でわかるようになりました！

## 要件
* ユーザー登録
* 本の検索
* 本の既読機能

## 実装する予定の機能についての説明
* ユーザー登録
- マイページを作ることで、誰にも見られない自分だけのページに移動することができます。見られたくないジャンルの漫画があっても安心！
* 本の検索
- タイトル検索をすることができ、なん巻まで買ったのかを確認することができます。
* 本の既読機能
- 投稿した本を読んだら、読んだチェックと星の数で評価と、コメントを投稿することができます。

## データベース設計
- ER図
https://gyazo.com/66a1a89bac8934a0dbee6d84140f8526

## ローカルでの動作方法
- git clone https://github.com/midor030/tukikage


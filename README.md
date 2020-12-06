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

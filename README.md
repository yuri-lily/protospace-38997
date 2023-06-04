#デーブル設計

## usersテーブル

| Column             | Type   | Option      |
| ------------------------------------------|
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |

## Association

- has_many  :prototypes
- has_many :comments


## prototypesテーブル

| Column             | Type      | Option      |
| ---------------------------------------------|
| title              | string    | null: false |
| catch_copy         | text      | null: false |
| concept            | text      | null: false |
| user               | reference | null: false |

## Association

- belong_to :user
- has_many  :comments


## commentsテーブル

| Column             | Type      | Option      |
| ---------------------------------------------|
| content            | text      | null: false |
| prototype          | reference | null: false |
| user               | reference | null: false |

## Association

- belong_to :user
- belong_to :prototype
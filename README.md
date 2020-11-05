# テーブル設計

## usersテーブル

| Column                   | Type   | Options                   |
| ------------------------ | ------ | ------------------------- |
| nickname                 | string | null: false               |
| email                    | string | null: false, unique: true |
| encrypted_password       | string | null: false               |
| last-name                | string | null: false               |
| first-name               | string | null: false               |
| last-name-kana           | string | null: false               |
| first-name-kana          | string | null: false               |
| user_birth_date_1i,2i,3i | date   | null: false               |

## itemsテーブル

| Column                  | Type    | Options                 |
| ----------------------- | ------- | ----------------------- |
| name                    | string  | null: false             |
| explain                 | text    | null: false             |
| category                | integer | null: false             |
| sales-status            | integer | null: false             |
| shipping-fee-status     | integer | null: false             |
| prefecture              | integer | null: false             |
| scheduled-delivery      | integer | null: false             |
| price                   | integer | null: false             |

## purchases

| Column                  | Type    | Options                 |
| ----------------------- | ------- | ----------------------- |
| postal-cord             | string  | null: false             |
| prefecture              | integer | null: false             |
| city                    | string  | null: false             |
| adderesses              | string  | null: false             |
| building                | string  |                         |
| phone-number            | string  | null: false             |

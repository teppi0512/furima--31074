# テーブル設計

## usersテーブル

| Column                  | Type   | Options     |
| ----------------------- | ------ | ----------- |
| nickname                | string | null: false |
| email                   | string | null: false |
| password                | string | null: false |
| password-confirmation   | string | null: false |
| last-name               | string | null: false |
| first-name              | string | null: false |
| last-name-kana          | string | null: false |
| first-name-kana         | string | null: false |
| user_birth_date_1i      | date   | null: false |
| user_birth_date_2i      | date   | null: false |
| user_birth_date_3i      | date   | null: false |

## itemsテーブル

| Column                  | Type   | Options                 |
| ----------------------- | ------ | ----------------------- |
| image                   | text   | null: false             |
| name                    | string | null: false             |
| explain                 | text   | null: false             |
| category                |        | null: false, select-box |
| sales-status            |        | null: false, select-box |
| shipping-fee-status     |        | null: false, select-box |
| prefecture              |        | null: false, select-box |
| scheduled-delivery      |        | null: false, select-box |
| price                   | text   | null: false             |

## purchases

| Column                  | Type   | Options                 |
| ----------------------- | ------ | ----------------------- |
| card-number             | string | null: false             |
| card-exp-mont           | string | null: false             |
| card-exp-year           | string | null: false             |
| card-cvc                | string | null: false             |
| postal-cord             | string | null: false             |
| prefecture              |        | null: false, select-box |
| city                    | string | null: false             |
| adderesses              | string | null: false             |
| building                | string |                         |
| phone-number            | string | null: false             |

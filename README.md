# テーブル設計

## usersテーブル

| Column                   | Type       | Options                        |
| ------------------------ | ---------- | ------------------------------ |
| nickname                 | string     | null: false                    |
| email                    | string     | null: false, unique: true      |
| encrypted_password       | string     | null: false                    |
| last_name                | string     | null: false                    |
| first_name               | string     | null: false                    |
| last-name_kana           | string     | null: false                    |
| first-name_kana          | string     | null: false                    |
| user_birth_date_1i,2i,3i | birth_date | null: false                    |

### Association

- has_many :items
- has_many :purchases

## itemsテーブル

| Column                  | Type    | Options                        |
| ----------------------- | ------- | ------------------------------ |
| name                    | string  | null: false                    |
| explain                 | text    | null: false                    |
| category_id             | integer | null: false, foreign_key: true |
| sales_status_id         | integer | null: false, foreign_key: true |
| shipping_fee_status_id  | integer | null: false, foreign_key: true |
| prefecture_id           | integer | null: false, foreign_key: true |
| scheduled_delivery_id   | integer | null: false, foreign_key: true |
| price                   | integer | null: false                    |

### Association

- has_many :users
- has_many :purchases

## purchases

| Column                  | Type       | Options                        |
| ----------------------- | ---------- | ------------------------------ |
| postal_cord_id          | string     | null: false                    |
| prefecture_id           | integer    | null: false, foreign_key: true |
| city                    | string     | null: false                    |
| adderesses              | string     | null: false                    |
| building                | string     |                                |
| phone_number            | string     | null: false                    |
| user_id                 | references |                                |
| item_id                 | references |                                |

### Association

- has_many :users
- has_many :items
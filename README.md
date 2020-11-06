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
| user_birth_date          | date       | null: false                    |

### Association

- has_many :items
- has_many :purchases

## itemsテーブル

| Column                  | Type    | Options                        |
| ----------------------- | ------- | ------------------------------ |
| name                    | string  | null: false                    |
| explain                 | text    | null: false                    |
| category_id             | integer | null: false                    |
| sales_status_id         | integer | null: false                    |
| shipping_fee_status_id  | integer | null: false                    |
| prefecture_id           | integer | null: false                    |
| scheduled_delivery_id   | integer | null: false                    |
| price                   | integer | null: false                    |

### Association

- belongs_to :users
- has_one :purchases

## purchases

| Column                  | Type       | Options                        |
| ----------------------- | ---------- | ------------------------------ |
| postal_cord_id          | string     | null: false                    |
| prefecture_id           | integer    | null: false                    |
| city                    | string     | null: false                    |
| adderesses              | string     | null: false                    |
| building                | string     |                                |
| phone_number            | string     | null: false                    |
| user                    | references |                                |
| item                    | references |                                |

### Association

- has_many :users
- has_many :items
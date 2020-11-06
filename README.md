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

| Column                  | Type       | Options                        |
| ----------------------- | ---------- | ------------------------------ |
| name                    | string     | null: false                    |
| explain                 | text       | null: false                    |
| category_id             | integer    | null: false                    |
| sales_status_id         | integer    | null: false                    |
| shipping_fee_status_id  | integer    | null: false                    |
| prefecture_id           | integer    | null: false                    |
| scheduled_delivery_id   | integer    | null: false                    |
| price                   | integer    | null: false                    |
| user                    | references |                                |

### Association

- belongs_to :user
- has_one :purchase

## purchasesテーブル

| Column                  | Type       | Options                        |
| ----------------------- | ---------- | ------------------------------ |
| user                    | references |                                |
| item                    | references |                                |

### Association

- belongs_to :user
- belongs_to :item

## purchase_usersテーブル

| Column                  | Type           | Options                        |
| ----------------------- | -------------- | ------------------------------ |
| postal_cord_id          | string         | null: false                    |
| prefecture_id           | integer        | null: false                    |
| city                    | string         | null: false                    |
| adderesses              | references     | null: false                    |
| building                | references     |                                |
| phone_number            | references     | null: false                    |

### Association

- belongs_to :purchase

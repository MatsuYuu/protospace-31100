# テーブル設計

## users テーブル

| Column    | Type   | Options     |
| --------  | ------ | ----------- |
| email     | string | NOT NULL    |
| password  | string | NOT NULL    |
| name      | string | NOT NULL    |
| profile   | text   | NOT NULL    |
| occupation| text   | NOT NULL    |
| position  | text   | NOT NULL    |

### Association

- has_many :prototype
- has_many :comments


## prototype テーブル

| Column    | Type         | Options     |
| --------  | ------------ | ----------- |
| title     | string       | NOT NULL    |
| catch_copy| text         | NOT NULL    |
| concept   | text         | NOT NULL    |
| image     |              |             |
| user      | references   |             |

### Association

- belongs_to :users
- has_many   :comments


## comments テーブル

| Column    | Type       | Options     |
| --------  | ---------- | ----------- |
| text      | text       | NOT NULL    |
| prototype | references |             |
| name      | references |             |

### Association

- belongs_to :users
- belongs_to :prototype
# データベース設計

##posts table

| Column | Type   | Options |
| ------ | ------ | ------- |
| title  | string |         |
| text   | text   |         |
| image  | text   |         |

### Association

- belongs_user :user
- has_many :tags through: :posts_tags

## users table

| Column   | type   | Options |
| -------- | ------ | ------- |
| nickname | string |         |

### Association

- has_many :posts

## tags table

| Column | type   | Options |
| ------ | ------ | ------- |
| name   | string |         |

### Association

- belongs_to :post through: :posts_tags

## posts_tags table

| Column  | type      | Options           |
| ------- | --------- | ----------------- |
| post_id | reference | foreign_key: true |
| tag_id  | reference | foreign_key: true |

### Association

- belongs_to :post
- belongs_to :tag

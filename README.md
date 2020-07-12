## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## userテーブル

|Column|Type|Options|
|------|----|-------|
|user|string|null: false|
|group_id|integer|null: false, foreign_key: true|

### Association
- has_many :groups_users
- has_many :group, through: :groups_users



## group

|Column|Type|Options|
|------|----|-------|
|group|string|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :groups_users
- has_many :user, through: :groups_users



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

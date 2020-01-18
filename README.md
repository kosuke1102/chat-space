## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|null: false, foreign_key: true|
|group_id|null: false, foreign_key: true|
|body|text||
|image|string||



### Association
- belongs_to: user
- belongs_to: group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|


### Association
- has_many: messages
- has_many: users ,through: groups_users
- has_many: groups_users

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, add_index: true|
|email|string|null: false, unique: true|

### Association
- has_many: messages
- has_many: groups,through: groups_users
- has_many: groups_users
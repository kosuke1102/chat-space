## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|reference|null: false, foreign_key: true|
|group_id|reference|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, index: true|
|group|references|null: false, index: true|
|body|references|null: false, index: true|
|image|references|null: false, index: true|


### Association
- belongs_to :groups_users
- belongs_to :group, through: :groups_users

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|references|null: false, index: true|

### Association
- has_many :messages
- has_many :users
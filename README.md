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
|user|reference|null: false, index: true|
|group|reference|null: false, index: true|

### Association
- has_many :groups_users
- has_many :group, through: :user_schools

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|user|reference|null: false, index: true|
|message|reference|null: false, index: true|

### Association
- has_many :groups_users
- has_many :messages, through: :user_schools
## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|comment|text|-------|
|img|string|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false|



### Association
- has_many :members
- has_many :users, through: :members
- has_many :users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false,add_index: true|
|password|integer|null: false,unique: true|
|mail_address|text|null: false,unique: true|

### Association
- has_many :groups, through: :members
- has_many :messages
- has_many :members

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

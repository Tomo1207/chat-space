## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|comment|text|-------|
|img|string|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belomgs_to :user
- has_many :groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false|



### Association
- has_many :members
- has_many :messages
- has_many :users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false|
|password|integer|null: false|
|mail_address|text|null: false|

### Association
- has_many :groups
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

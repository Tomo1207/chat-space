## messageテーブル

|Column|Type|Options|
|------|----|-------|
|comment|text|-------|
|img|string|-------|
|user_id|integer|
|group_id|integer|

### Association
- belomgs_to :group_members
- belongs_to :group

## groupテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|

### Association
- has_many :member
- has_many :message
- belongs_to :user

## userテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|
|password|
|mail_address|

### Association
- has_many :group
- has_many :message
- belongs_to :member

## group_membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- has_many :message

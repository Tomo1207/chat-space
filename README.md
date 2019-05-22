## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## groupテーブル


### Association
- has_many :members
- belongs_to :user


## userテーブル


### Association
- has_many :group
- has_many :members
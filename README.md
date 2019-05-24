
## groupテーブル

|Column|Type|Options|
|------|----|-------|

### Association
- has_many :members
- belongs_to :user


## userテーブル

|Column|Type|Options|
|------|----|-------|

### Association
- has_many :group
- has_many :members

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

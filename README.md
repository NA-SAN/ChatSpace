# DB設計

## users table

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|name|string|index: true, null: false, unique: true|
|password|integer|
|mail|string|null: false|
|group_id|integer|null: false, foreign_key: true|
|message_id|integer|null: false, foreign_key: true|


### Association
- has_many :group
- has_many :messages


## group table

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|group_name|string|null: falese, foreign_key: true|
|user_id|integer|hull:falese, forein_key: true|

### Association
- has_many :users, thought: :users_group
- has_many :users_group


##users_goups

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :users
- belongs_to :groups


## message table

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :users



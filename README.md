# DB設計

## users table

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|
|password|integer|null: false|
|mail|string|null: false|
|group_id|references|null: false, foreign_key: true|
|message_id|references|null: false, foreign_key: true|


### Association
- has_many :group
- has_many :messages


## group table

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: falese, foreign_key: true|
|user_id|references|hull:falese, forein_key: true|

### Association
- has_many :users, thought: :users_group
- has_many :users_group
- has_many :messages


##users_goups

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :users
- belongs_to :groups


## message table

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|

### Association
- belongs_to :users
- belongs_to :groups


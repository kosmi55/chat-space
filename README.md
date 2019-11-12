# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :groups,  through:  :users_groups
- has_many :users_groups
- has_many :messages


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|title|text|null: false|

### Association
- has_many :users,  through:  :users_groups
- has_many :messages
- has_many :users_groups


## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

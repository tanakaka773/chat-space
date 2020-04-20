## Chat-space
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
### Association
- has_many :messages|
- has_many :groups_users
- has_many :users, through: :grops_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text|
|img|string|
|group_id|integer|null: false|
|user_id|integer|null: false|
### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false,foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
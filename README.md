# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
### Association
-has_many :groups, through:  :users_groups
-has_may :posts

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
### Association
-has_many :users, through: :users_groups
-has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group


# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: ture|
|email|string|null: false|
### Association
-has_many :users_groups
-has_many :groups, through:  :users_groups
-has_may :posts

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|users_id|references|null: false, foreign_key: true|
|groups_id|references|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
-has_many :users_groups
-has_many :users, through: :users_groups
-has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|string||
|users_id|references|null: false, foreign_key: true|
|groups_id|references|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group


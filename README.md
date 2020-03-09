# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
<<<<<<< HEAD
|name|string|null: false|
|email|string|null: false|
### Association
=======
|name|string|null: false, index: ture|
|email|string|null: false|
### Association
-has_many :users_groups
>>>>>>> e3704f4c00667f307810154ebaa96641418e454e
-has_many :groups, through:  :users_groups
-has_may :posts

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
<<<<<<< HEAD
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
=======
|users_id|references|null: false, foreign_key: true|
|groups_id|references|null: false, foreign_key: true|
>>>>>>> e3704f4c00667f307810154ebaa96641418e454e
### Association
-belongs_to :user
-belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
<<<<<<< HEAD
|groupname|string|null: false|
### Association
=======
|name|string|null: false|
### Association
-has_many :users_groups
>>>>>>> e3704f4c00667f307810154ebaa96641418e454e
-has_many :users, through: :users_groups
-has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
<<<<<<< HEAD
|text|text|null: false|
|users_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group
=======
|text|text||
|image|string||
|users_id|references|null: false, foreign_key: true|
|groups_id|references|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group

>>>>>>> e3704f4c00667f307810154ebaa96641418e454e

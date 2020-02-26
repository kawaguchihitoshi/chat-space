## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false,index: true|
### Association
- has_many :messages
- has_many :users_groups
- has_many  :groups, through: :users_group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
### Association
- has_many :messages
- has_many :users_groups
- has_many  :users, through: :users_group

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string||
|text|text||
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

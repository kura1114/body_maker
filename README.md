# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nick_name|string|null: false|
|mail|string|null: false, unique: true|


## targetテーブル
|Column|Type|Options|
|------|----|-------|
|target|string|null: false, unique: true|
|deadline|integer|null: false|
|feedback|integer|null: false|
|remind|integer|null: false|
|rate|integer|null: false|
|user_id|references|null: false, foreign_key: true|

### Association
- has_many :to_dos

## to_dosテーブル
|Column|Type|Options|
|------|----|-------|
|if|string|null, false|
|then|string|null, false|
|remind|integer|null, false|
|target_id|references|null, false, foreign_key: true|

### Association
- belongs_to :target
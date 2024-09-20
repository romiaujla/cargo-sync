[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `user`

## Description

Represents a `user` in the system. The `user` table stores all the information related to a user, including their unique identifier, name, email, and other relevant details. This table is  essential for managing user data and authentication within the application.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`user_id`|Primary key|`integer`|❌||
|`username`|Unique username for the user|`varchar(255)`|❌||
|`password_hash`|Hashed password for the user|`varchar(255)`|❌||
|`email`|User's email address|`varchar(255)`|❌||
|`first_name`|User's first name|`varchar(50)`|❌||
|`middle_name`|User's middle name|`varchar(50)`|✓||
|`last_name`|User's last name|`varchar(50)`|❌||
|`nick_name`|User's nick name|`varchar(50)`|✓||
|`phone`|User's phone number|`varchar(20)`|✓||
|`address`|User's address|`varchar(255)`|✓||
|`address_2`|User's address line 2|`varchar(255)`|✓||
|`city`|User's city|`varchar(255)`|✓||
|`state`|User's state|`varchar(50)`|✓||
|`zip`|User's zip code|`varchar(10)`|✓||
|`country`|User's country|`varchar(100)`|✓||
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_user_id`|`primary key`|Primary key constraint|`user_id`|
|`uq_user_username`|`unique`|Ensures that each username in the user table is unique|`username`|
|`uq_user_email`|`unique`|Ensures that each email in the user table is unique|`email`|
|`chk_user_email`|`check`|Ensures that the email column contains a valid email format|`email`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|`idx_user_username`|Index on the username column for faster lookups|`username`|
|`idx_user_email`|Index on the email column for faster lookups|`email`|
|`idx_user_phone`|Index on the phone column for faster lookups|`phone`|

## Relationships

|Table Name|Relation*|
|-|-|
|[`user_note`](./user-note-table.md)|One is to many|
|[`user_role`](./user-role-table.md)|Many to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
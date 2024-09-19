[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `user_note`

## Description
The `user_note` table stores notes associated with users. Each note is linked to a specific user and contains information about the note's content, creation, and modification details. This table is useful for applications that need to keep track of user-specific notes or comments.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`user_note_id`|Primary key|`integer`|❌||
|`fk_user_id`|Foreign key to the `user` table|`integer`|❌||
|`fk_note_id`|Foreign key to the `note` table|`integer`|❌||
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|
|&nbsp;|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_user_note`|`primary key`|Primary key constraint|`user_note_id`|
|`fk_user_note_user`|`foreign key`|Foreign key constraint linking to `user` table|`fk_user_id`|
|`fk_user_note_note`|`foreign key`|Foreign key constraint linking to `note` table|`fk_note_id`|

## Indexes

## Relationships

|Table Name|Relation (`user_note : note`)|
|-|-|
|[`note`](./note-table.md)|Many is to one|
|[`user`](./user-table.md)|Many is to one|


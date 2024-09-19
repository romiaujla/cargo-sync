[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `user_role`

## Description
The `user_role` table stores roles associated with users. Each role is linked to a specific user and contains information about the role's content, creation, and modification details. This table is useful for applications that need to keep track of user-specific roles or comments.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`user_role_id`|Primary key|`integer`|❌||
|`fk_user_id`|Foreign key to the `user` table|`integer`|❌||
|`fk_role_id`|Foreign key to the `role` table|`integer`|❌||
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
|`pk_user_role`|`primary key`|Primary key constraint|`user_role_id`|
|`fk_user_role_user`|`foreign key`|Foreign key constraint linking to `user` table|`fk_user_id`|
|`fk_user_role_role`|`foreign key`|Foreign key constraint linking to `role` table|`fk_role_id`|

## Indexes

## Relationships

|Table Name|Relation*|
|-|-|
|[`role`](./role-table.md)|Many is to one|
|[`user`](./user-table.md)|Many is to one|

<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
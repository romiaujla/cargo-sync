[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load_note`

## Description

The `load_note` table stores information related to notes associated with loads.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_note_id`|Primary key|`integer`|❌||
|`fk_user_id`|Foreign key to the `user` table|`integer`|❌||
|`fk_note_id`|Foreign key to the `note` table|`integer`|❌||
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
|`pk_load_note_id`|`primary key`|Primary key constraint|`load_note_id`|
|`fk_load_note_load_id`|`foreign key`|Foreign key constraint linking to `load` table|`fk_load_id`|
|`fk_load_note_note_id`|`foreign key`|Foreign key constraint linking to `note` table|`fk_note_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`note`](./note-table.md)|Many is to one|
|[`load`](./load-table.md)|Many is to one|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
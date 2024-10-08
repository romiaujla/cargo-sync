[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `{table}_note`

## Description

The `{table}_note` table serves as a junction table linking {table}s and notes. It stores metadata about the associations between {table}s and various notes, including timestamps for creation, updates, and deletions. This table helps in organizing and managing the relationships between {table}s and their associated notes efficiently within the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`{table}_note_id`|Primary key|`integer`|❌||
|`fk_{table}_id`|Foreign key to the `{table}` table|`integer`|❌||
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
|`pk_{table}_note_id`|`primary key`|Primary key constraint|`{table}_note_id`|
|`fk_{table}_note_user`|`foreign key`|Foreign key constraint linking to `{table}` table|`fk_{table}_id`|
|`fk_{table}_note_note`|`foreign key`|Foreign key constraint linking to `note` table|`fk_note_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`{table}`](./{table}-table.md)|Many is to one|
|[`note`](./note-table.md)|Many is to one|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
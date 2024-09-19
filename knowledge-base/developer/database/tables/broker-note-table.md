[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `broker_note`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`broker_note_id`|Primary key|`integer`|❌||
|`fk_broker_id`|Foreign key to the `broker` table|`integer`|❌||
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
|`pk_broker_note_id`|`primary key`|Primary key constraint|`broker_note_id`|
|`fk_broker_note_user`|`foreign key`|Foreign key constraint linking to `broker` table|`fk_broker_id`|
|`fk_broker_note_note`|`foreign key`|Foreign key constraint linking to `note` table|`fk_note_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`broker`](./broker-table.md)|Many is to one|
|[`note`](./note-table.md)|Many is to one|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `trailer_note`

## Description

The `trailer_note` table serves as a junction table linking trailers and notes. It stores metadata about the associations between trailers and various notes, including timestamps for creation, updates, and deletions. This table helps in organizing and managing the relationships between trailers and their associated notes efficiently within the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`trailer_note_id`|Primary key|`integer`|❌||
|`fk_trailer_id`|Foreign key to the `trailer` table|`integer`|❌||
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
|`pk_trailer_note_id`|`primary key`|Primary key constraint|`trailer_note_id`|
|`fk_trailer_note_user`|`foreign key`|Foreign key constraint linking to `trailer` table|`fk_trailer_id`|
|`fk_trailer_note_note`|`foreign key`|Foreign key constraint linking to `note` table|`fk_note_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`trailer`](./trailer-table.md)|Many is to one|
|[`note`](./note-table.md)|Many is to one|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
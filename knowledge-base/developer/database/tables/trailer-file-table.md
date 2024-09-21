[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `trailer_file`

## Description

The `trailer_file` table serves as a junction table linking trailers and files. It stores metadata about the associations between trailers and various files, including timestamps for creation, updates, and deletions. This table helps in organizing and managing the relationships between trailers and their associated files efficiently within the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`trailer_file_id`|Primary key|`integer`|❌||
|`fk_trailer_id`|Foreign key to the `trailer` table|`integer`|❌||
|`fk_file_id`|Foreign key to the `file` table|`varchar(100)`|❌||
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
|`pk_trailer_file_id`|`primary key`|Primary key constraint|`trailer_file_id`|
|`fk_trailer_file_trailer_id`|`foreign key`|Foreign key constraint referencing `trailer` table|`fk_trailer_id`|
|`fk_trailer_file_file_id`|`foreign key`|Foreign key constraint referencing `file` table|`fk_file_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`trailer`](./trailer-table.md)|Many-to-One|
|[`file`](./file-table.md)|Many-to-One|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
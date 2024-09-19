[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `table_name`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`table_name_id`|Primary key|`integer`|❌||
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
|`pk_table_name_id`|`primary key`|Primary key constraint|`table_name_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|`idx_table_name_username`|Index description|`username`|

## Relationships

|Table Name|Relation*|
|-|-|
|[`table_name_note`](./link.md)|One is to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
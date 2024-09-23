[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `invoice`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`invoice_id`|Primary key|`integer`|❌||
|`fk_load_id`|Foreign key to the `load` table|`integer`|❌||
|`fk_broker_id`|Foreign key to the `broker` table|`integer`|❌||
|`is_paid`|Indicates if the invoice has been paid.|`boolean`|❌|`false`|
|`due_date`|The date by which the invoice should be paid.|`date`|❌||
|`amount`|Total amount of the invoice.|`decimal(10,2)`|❌||
|`currency`|Currency of the invoice amount.|`varchar(3)`|❌|`USD`|
|`description`|Description or notes about the invoice.|`text`|✓|`null`|
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
|`pk_invoice_id`|`primary key`|Primary key constraint|`invoice_id`|
|`fk_invoice_load_id`|`foreign key`|Foreign key constraint|`fk_load_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load`](./load-table.md)|One is to One|
|[`broker`](./broker-table.md)|Many is to One|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
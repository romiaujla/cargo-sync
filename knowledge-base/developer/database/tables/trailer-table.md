[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `trailer`

## Description

The `trailer` table stores information about trailers used in logistics and transportation. Each record represents a unique trailer and includes metadata about its creation, updates, and deletion.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`trailer_id`|Primary key|`integer`|❌||
|`unit_number`|Unique identifier assigned to the trailer.|`varchar(50)`|❌||
|`vin_number`|Vehicle Identification Number.|`varchar(17)`|❌||
|`manufacturer`|Name of the trailer's manufacturer.|`varchar(100)`|❌||
|`model`|Model of the trailer.|`varchar(100)`|❌||
|`year`|Year of manufacture.|`integer`|❌||
|`purchase_date`|Date when the trailer was purchased.|`date`|❌||
|`license_plate`|License plate number.|`varchar(20)`|❌||
|`registered_state`|State where the trailer is registered.|`varchar(50)`|❌||
|`color`|Color of the trailer.|`varchar(30)`|❌||
|`type`|Type of the trailer (e.g., flatbed, refrigerated).|`varchar(50)`|❌||
|`length`|Length of the trailer in feet.|`integer`|❌||
|`axle_count`|Number of axles on the trailer.|`integer`|❌||
|`last_service_date`|Date when the trailer was last serviced.|`date`|✓|`null`|
|`next_service_date`|Date when the trailer is due for the next service.|`date`|✓|`null`|
|`warranty_expiration_date`|Warranty expiration date.|`date`|✓|`null`|
|`insurance_expiration_date`|Date when the insurance expires.|`date`|✓|`null`|
|`is_active`|Indicates if the trailer is currently active.|`boolean`|❌|`true`|
|`sold_date`|Date when the trailer was sold.|`date`|✓|`null`|
|`purchase_price`|Price at which the trailer was purchased.|`decimal(10,2)`|✓|`null`|
|`sold_price`|Price at which the trailer was sold.|`decimal(10,2)`|✓|`null`|
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
|`pk_trailer_id`|`primary key`|Primary key constraint|`trailer_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_log`](./load-log-table.md)|One is to many|
|[`trailer_file`](./trailer-file-table.md)|One is to many|
|[`trailer_note`](./trailer-note-table.md)|One is to many|

<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
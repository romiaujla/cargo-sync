[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `tractor`

## Description

The `tractor` table stores detailed information about each tractor in the fleet. It includes identifiers, specifications, service records, and status indicators to manage and track the lifecycle and usage of each tractor.


## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`tractor_id`|Primary key|`integer`|❌||
|`unit_number`|Unique identifier for the tractor unit.|`varchar(50)`|❌||
|`vin_number`|Vehicle Identification Number.|`varchar(17)`|❌||
|`manufacturer`|Manufacturer of the tractor.|`varchar(100)`|❌||
|`model`|Model of the tractor.|`varchar(100)`|❌||
|`year`|Year of manufacture.|`integer`|❌||
|`purchase_date`|Date when the tractor was purchased.|`date`|❌||
|`purchase_mileage`|Mileage at the time of purchase.|`integer`|❌|`0`|
|`license_plate`|License plate number.|`varchar(20)`|❌||
|`registered_state`|State where the tractor is registered.|`varchar(50)`|❌||
|`color`|Color of the tractor.|`varchar(30)`|❌||
|`engine_type`|Type of engine used in the tractor.|`varchar(50)`|❌||
|`horsepower`|Horsepower of the tractor.|`integer`|❌||
|`mileage`|Mileage of the tractor.|`integer`|❌|`0`|
|`last_service_date`|Date of the last service.|`date`|✓|`null`|
|`last_service_mileage`|Mileage at the time of the last service.|`integer`|✓|`null`|
|`next_service_date`|Date of the next scheduled service.|`date`|✓|`null`|
|`next_service_mileage`|Mileage at which the next service is due.|`integer`|✓|`null`|
|`warranty_expiration_date`|Warranty expiration date.|`date`|✓|`null`|
|`insurance_expiration_date`|Date when the insurance expires.|`date`|✓|`null`|
|`is_active`|Indicates if the tractor is currently active.|`boolean`|❌|`true`|
|`sold_date`|Date when the tractor was sold.|`date`|✓|`null`|
|`purchase_price`|Price at which the tractor was purchased.|`decimal(10,2)`|✓|`null`|
|`sold_price`|Price at which the tractor was sold.|`decimal(10,2)`|✓|`null`|
|`fuel_card_number`|Fuel card number assigned to the tractor.|`varchar(50)`|✓|`null`|
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
|`pk_tractor_id`|`primary key`|Primary key constraint|`tractor_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_log`](./load-log-table.md)|One is to many|
|[`tractor_file`](./tractor-file-table.md)|One is to many|
|[`tractor_note`](./tractor-note-table.md)|One is to many|




<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
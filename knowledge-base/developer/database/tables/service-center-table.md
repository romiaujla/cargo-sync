[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `service_center`

## Description
The `service_center` table stores information about various service centers. Each record in the table represents a service center with details such as its name, location, contact information, and operational hours. This table is essential for managing and querying data related to service centers within the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`service_center_id`|Primary key|`integer`|❌||
|`name`|Name of the service center.|`varchar(255)`|❌||
|`address`|Street address of the service center.|`varchar(255)`|❌||
|`address_2`|Additional address information.|`varchar(255)`|✓|`null`|
|`city`|City where the service center is located.|`varchar(100)`|❌||
|`state`|State where the service center is located.|`varchar(100)`|❌||
|`zip`|ZIP code of the service center.|`varchar(20)`|❌||
|`country`|Country where the service center is located.|`varchar(100)`|❌||
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
|`pk_service_center_id`|`primary key`|Primary key constraint|`service_center_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|`idx_service_center_username`|Index description|`username`|

## Relationships

|Table Name|Relation*|
|-|-|
|[`service_center_note`](./service-center-note-table.md)|One is to many|
|[`service_center_specialty`](./service-center-specialty-table.md)|One is to many|
|[`service_center_contact`](./service-center-contact-table.md)|One is to many|
|[`tractor_service_log`](./tractor-service-log-table.md)|One is to many|
|[`trailer_service_log`](./trailer-service-log-table.md)|One is to many|



<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
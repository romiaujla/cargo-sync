[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `tractor_service_log`

## Description

The `tractor_service_log` table is used to record and track the maintenance and service activities performed on tractors. It includes details such as service dates, costs, descriptions, and statuses to ensure comprehensive documentation of each service event.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`tractor_service_log_id`|Primary key|`integer`|❌||
|`fk_service_center_id`|Foreign key referencing the `service_center` table.|`integer`|❌||
|`fk_tractor_id`|Foreign key referencing the `tractor` table.|`integer`|❌||
|`fk_service_center_contact_id_technician`|Foreign key referencing the `service_center_contact` table for the technician.|`integer`|✓|`null`|
|`start_date`|Date when the service started.|`date`|❌||
|`end_date`|Date when the service ended.|`date`|❌||
|`estimate_cost`|Estimated cost of the service.|`decimal(10,2)`|✓|`null`|
|`actual_cost`|Actual cost of the service.|`decimal(10,2)`|✓|`null`|
|`description`|Description of the service performed.|`text`|✓|`null`|
|[`status`](#status)|Status of the service (e.g., pending, completed).|`varchar(50)`|❌|`Pending`|
|`parts_replaced`|List of parts replaced during the service.|`text`|✓|`null`|
|`warranty_expiration_date`|Expiration date of the warranty for the service.|`date`|✓|`null`|
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|

## Enums

### `status`

|Value|Description|
|-|-|
|`Pending`|Service is scheduled but not yet started.|
|`Pending Approval`|Service is pending approval from a supervisor.|
|`In Progress`|Service is currently being performed.|
|`On Hold`|Service is temporarily paused.|
|`On Hold Parts`|Service is on hold due to parts unavailability.|
|`Completed`|Service has been completed.|
|`Cancelled`|Service was cancelled before completion.|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_tractor_service_log_id`|`primary key`|Primary key constraint|`tractor_service_log_id`|
|`fk_service_center_id`|`foreign key`|Foreign key constraint|`fk_service_center_id`|
|`fk_tractor_id`|`foreign key`|Foreign key constraint|`fk_tractor_id`|
|`fk_service_center_contact_id_technician`|`foreign key`|Foreign key constraint|`fk_service_center_contact_id_technician`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`tractor`](./tractor-table.md)|Many is to one|
|[`service_center`](./service-center-table.md)|Many is to one|
|[`service_center_contact`](./service-center-contact-table.md)|Many is to one|



<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
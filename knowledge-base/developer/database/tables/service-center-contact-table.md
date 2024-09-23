[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `service_center_contact`

## Description
This document provides details about the Service Center Contact Table. It includes information on the structure and fields of the table used to store contact details for service centers.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`service_center_contact_id`|Primary key|`integer`|❌||
|`fk_service_center_id`|Foreign key referencing the `service_center` table.|`integer`|❌||
|`first_name`|First name of the service center contact.|`varchar`|❌||
|`middle_name`|Middle name of the service center contact.|`varchar`|✓|`null`|
|`last_name`|Last name of the service center contact.|`varchar`|❌||
|`nick_name`|Nick name of the service center contact.|`varchar`|✓|`null`|
|`email`|Email address of the service center contact.|`varchar`|❌||
|`phone`|Phone number of the service center contact.|`varchar`|❌||
|`fax`|Fax number of the service center contact.|`varchar`|✓|`null`|
|`address`|Primary address of the service center contact.|`varchar`|✓|`null`|
|`address_2`|Secondary address of the service center contact.|`varchar`|✓|`null`|
|`city`|City of the service center contact.|`varchar`|✓|`null`|
|`state`|State of the service center contact.|`varchar`|✓|`null`|
|`zip`|ZIP code of the service center contact.|`varchar`|✓|`null`|
|`country`|Country of the service center contact.|`varchar`|✓|`null`|
|[`designation`](#designation)|Designation of the service center contact.|`varchar`|✓|`null`|
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|


## Enums

### `designation`

|Value|Description|
|-|-|
|`Owner`|Owner of the brokerage firm|
|`Manager`|Manager at the brokerage firm|
|`Technician`|Technician at the service center|
|`Receptionist`|Receptionist at the service center|
|`Customer Service`|Customer service representative at the service center|
|`Sales`|Sales representative at the service center|
|`Administrator`|Administrator at the service center|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_service_center_contact_id`|`primary key`|Primary key constraint|`service_center_contact_id`|
|`fk_service_center_id`|`foreign key`|Foreign key constraint|`fk_service_center_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`service_center`](./service-center-table.md)|Many-to-One|
|[`tractor_service_log`](./tractor-service-log-table.md)|One-to-Many|
|[`trailer_service_log`](./trailer-service-log-table.md)|One-to-Many|

<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
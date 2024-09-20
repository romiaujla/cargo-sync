[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `broker_contact`

## Description

This table represents a collection of users and their associated details. It includes columns for user ID, name, email, and registration date.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`broker_contact_id`|Primary key|`integer`|❌||
|`fk_broker_id`|Foreign key referencing the `broker` table.|`integer`|❌||
|`first_name`|First name of the broker contact.|`varchar`|❌||
|`middle_name`|Middle name of the broker contact.|`varchar`|✓|`null`|
|`last_name`|Last name of the broker contact.|`varchar`|❌||
|`nick_name`|Nick name of the broker contact.|`varchar`|✓|`null`|
|`email`|Email address of the broker contact.|`varchar`|❌||
|`phone`|Phone number of the broker contact.|`varchar`|❌||
|`fax`|Fax number of the broker contact.|`varchar`|✓|`null`|
|`address`|Primary address of the broker contact.|`varchar`|✓|`null`|
|`address_2`|Secondary address of the broker contact.|`varchar`|✓|`null`|
|`city`|City of the broker contact.|`varchar`|✓|`null`|
|`state`|State of the broker contact.|`varchar`|✓|`null`|
|`zip`|ZIP code of the broker contact.|`varchar`|✓|`null`|
|`country`|Country of the broker contact.|`varchar`|✓|`null`|
|`designation`|Designation of the broker contact.|`varchar`|✓|`null`|
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
|`Load Agent`|Agent representing the brokerage firm|
|`Accounts Receivable`|Manager of accounts receivable|


## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_broker_contact_id`|`primary key`|Primary key constraint|`broker_contact_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`broker`](./broker-table.md)|Many to one|
|[`load_broker_contact`](./load_broker_contact-table.md)|One to many|



<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
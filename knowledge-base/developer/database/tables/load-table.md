[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load`

## Description
The `load` table contains information about a load being transported by the company.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_id`|Primary key|`integer`|❌||
|`load_number`|Load number assigned by the broker|`varchar(255)`|❌||
|`fk_broker_id`|Foreign key to the `broker` table|`integer`|❌||
|`fk_user_id_dispatcher`|Foreign key to the `user` table, for the dispatcher that booked the load|`integer`|❌||
|`fk_load_broker_contact_id`|Foreign key to the `load_broker_contact` table, contact of the people to reach out to incase of conducting business with the broker who provided the load|`integer`|❌||
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
|`pk_load_id`|`primary key`|Primary key constraint|`load_id`|
|`fk_broker_id`|`foreign key`|Foreign key constraint to the `broker` table|`fk_broker_id`|
|`fk_user_id_dispatcher`|`foreign key`|Foreign key constraint to the `user` table|`fk_user_id_dispatcher`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_note`](./load-note-table.md)|One is to Many|
|[`load_log`](./load-log-table.md)|One is to Many|
|[`load_stop`](./load-stop-table.md)|One is to Many|
|[`broker`](./broker-table.md)|Many is to One|
|[`load_broker_contact`](./broker-contact-table.md)|One is to Many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
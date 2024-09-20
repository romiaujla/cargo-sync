[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load_broker_contact`

## Description

This table serves as a junction table to manage the many-to-many relationship between a load and a broker contact. It ensures that each load can be associated with multiple broker contacts and each broker contact can be linked to multiple loads. This relationship is crucial for maintaining the flexibility and scalability of the database schema, allowing efficient management of load and broker contact associations.


## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_broker_contact_id`|Primary key|`integer`|❌||
|`fk_load_id`|Foreign key to the `load` table|`integer`|❌||
|`fk_broker_contact_id`|Foreign key to the `broker_contact` table|`integer`|❌||
|`is_primary`|Indicates if the contact is the primary contact|`boolean`|❌|`false`|
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
|`pk_load_broker_contact_id`|`primary key`|Primary key constraint|`load_broker_contact_id`|
|`fk_load_broker_contact_load_id`|`foreign key`|Foreign key constraint to the `load` table|`fk_load_id`|
|`fk_load_broker_contact_broker_contact_id`|`foreign key`|Foreign key constraint to the `broker_contact` table|`fk_broker_contact_id`|


## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load`](./load-table.md)|Many to One|
|[`broker_contact`](./broker-contact-table.md)|Many to One|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
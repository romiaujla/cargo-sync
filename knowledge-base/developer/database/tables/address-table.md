[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `address`

## Description
This table is used for storing all the pick-up and drop-off addresses associated with various loads. Each entry in the table represents a unique address that can be referenced for pick-up or drop-off purposes. This table is essential for managing logistics and ensuring accurate tracking of pick-up and drop-off locations in the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`address_id`|Primary key|`integer`|❌||
|`address`|Address line 1|`varchar(255)`|✓|`null`|
|`address_2`|Address line 2|`varchar(255)`|✓|`null`|
|`city`|City|`varchar(255)`|✓|`null`|
|`state`|State|`varchar(50)`|✓|`null`|
|`zip`|Zip code|`varchar(10)`|✓|`null`|
|`country`|Country|`varchar(100)`|✓|`null`|
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
|-|-|-|-|
|`pk_address_id`|`primary key`|Primary key constraint|`address_id`|
|`uq_address`|`unique`|Ensures that the combination of address, city, state, and zip is unique|`address`, `city`, `state`, `zip`|

## Indexes


|Index Name|Description|Column(s)|
|-|-|-|
|`idx_address_city`|Index on the city column for faster searches by city|`city`|
|`idx_address_state`|Index on the state column for faster searches by state|`state`|
|`idx_address_zip`|Index on the zip column for faster searches by zip code|`zip`|



## Relationships

|Table Name|Relation*|
|-|-|
|[`address_note`](./address-note-table.md)|One is to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>

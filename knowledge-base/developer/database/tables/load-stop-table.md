[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load_stop`

## Description

The `load_stop` table is used to record the stops associated with a load in a logistics system. Each stop represents a point where a load is either picked up or dropped off. The table includes details such as the start and end timestamps of the stop, the type of stop (pick-up or drop-off), and references to other related tables like `load` and `address`. It also supports self-referencing to create a chain of stops.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_stop_id`|Primary key|`integer`|❌|`auto generated`|
|`fk_load_id`|Foreign key to the `load` table|`integer`|❌||
|`fk_address_id`|Foreign key to the `address` table|`integer`|❌||
|`fk_load_stop_id_previous`|Self referencing foreign key to the `load_stop` table, this will be user to create a chain of stops|`integer`|✓|`null`|
|`start_at`|Timestamp when the stop starts.|`timestamp`|❌|`null`|
|`end_at`|Timestamp when the stop ends.|`timestamp`|❌|`null`|
|[`type`](#type)|Type of the load whether a Pick Up or Drop Off|`varchar(15)`|❌|`Pick Up`|
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|

## Enums

### `type`

|Value|Description|
|-|-|
|`Pick Up`|Represents a pick-up stop|
|`Drop Off`|Represents a drop-off stop|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_load_stop_id`|`primary key`|Primary key constraint|`load_stop_id`|
|`fk_load_stop_load_id`|`foreign key`|Foreign key constraint to the `load` table|`fk_load_id`|
|`fk_load_stop_address_id`|`foreign key`|Foreign key constraint to the `address` table|`fk_address_id`|
|`fk_load_stop_id_previous`|`foreign key`|Self-referencing foreign key constraint to the `load_stop` table|`fk_load_stop_id_previous`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load`](./load-table.md)|Many is to One|
|[`address`](./address-table.md)|Many is to One|
|[`load_stop`](./load-stop-table.md)|One is to One (Self)|
|[`load_log`](./load-log-table.md)|One is to Many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
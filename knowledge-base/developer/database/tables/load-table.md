[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_id`|Primary key|`integer`|❌||
|`load_number`|Load number assigned by the broker|`varchar(255)`||❌||
|`fk_broker_id`|Foreign key to the `broker` table|`integer`|❌||
|`fk_user_id_dispatcher`|Foreign key to the `user` table, for the dispatcher that booked the load|`integer`|❌||
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|



<!-- ## Enums
Move to load_status_log
### `status`
this will also contain info for the tractor and trailer assigned, and must have a status
- tractor re-assignment
- driver re-assignment
- delivery location re-assignment
- pick-up location re-assignment


|Value|Description|
|-|-|
|`pending confirmation`|A new load is entered into the system, is still pending the load confirmation to be signed|
|`load confirmed`|Once the load has confirmation has been signed between the carrier and the broker|
|`scheduled`|All the necessary information about the load (pick-up/delivery location, weight, type of cargo, etc.) is entered into the system, and the shipment is assigned to a driver/truck.|
|`driver accepted`|Once the driver accepts the assignment, the load is confirmed for pick-up|
|`truck dispatched`|The driver received the instructions, and the system updates the load status to show that the truck is en route to the pick-up.|
|`at pick up location`|The driver has arrived at the pick-up location and is ready to load the cargo.|
|`loading in progress`|The cargo is being loaded onto the truck.|
|`in transit`| -->

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_load_id`|`primary key`|Primary key constraint|`load_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_note`](./load-note-table.md)|One is to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
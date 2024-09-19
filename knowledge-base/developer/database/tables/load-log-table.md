[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load_log`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_log_id`|Primary key|`integer`|❌||
|`fk_load_id`|Foreign key to the `load` table|`integer`|❌||
|[`status`](#status)|Status of the load|`varchar(100)`|❌||
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
|`Pending Confirmation`|A new load is entered into the system, is still pending the load confirmation to be signed|
|`Load Confirmed`|Once the load has confirmation has been signed between the carrier and the broker|
|`Scheduled`|All the necessary information about the load (pick-up/delivery location, weight, type of cargo, etc.) is entered into the system, and the shipment is assigned to a driver/truck.|
|`Driver Accepted`|Once the driver accepts the assignment, the load is confirmed for pick-up|
|`Truck Dispatched`|The driver received the instructions, and the system updates the load status to show that the truck is en route to the pick-up.|
|`At Pick Up`|The driver has arrived at the pick-up location and is ready to load the cargo.|
|`Loading`|The cargo is being loaded onto the truck.|
|`In Transit`|The truck is on the way to the delivery location.|
|`Resting`|The driver is taking a mandatory rest break.|
|`At Drop Off`|The driver has arrived at the delivery location and is ready to unload the cargo.|
|`Unloading`|The cargo is being unloaded from the truck.|
|`Complete`|The delivery has been completed successfully.|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_load_log_id`|`primary key`|Primary key constraint|`load_log_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|`idx_load_log_username`|Index description|`username`|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_log_note`](./link.md)|One is to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
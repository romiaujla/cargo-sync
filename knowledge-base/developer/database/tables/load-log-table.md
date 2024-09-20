[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `load_log`

## Description

The `load_log` table is designed to maintain the different stages a load goes through from start to finish. It provides a historical record of the load's status changes, capturing key events and timestamps. This information is crucial for tracking the progress of a load, identifying delays, and ensuring transparency in the load management process.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`load_log_id`|Primary key|`integer`|❌||
|`fk_load_id`|Foreign key to the `load` table|`integer`|❌||
|[`status`](#status)|Status of the load|`varchar(100)`|❌||
|`fk_load_stop_id`|Foreign key to the `load` table. This will be required when the status is `At Pick Up`, `Loading`, `At Drop Off` and `Unloading`|`integer`|✓|`null`|
|`start_at`|Timestamp when the load started.|`timestamp`|❌|`null`|
|`end_at`|Timestamp when the load ended.|`timestamp`|❌|`null`|
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
|`Pre-Trip`|The driver is performing a pre-trip inspection of the truck and cargo.|
|`Inspection`|The truck and cargo are being inspected, usually by a regulatory authority.|
|`Fuel Stop`|The truck is stopping for refueling.|
|`Breakdown`|The truck has encountered a mechanical issue and is unable to continue.|
|`Driver Reassignment`|The current driver is being replaced with another driver.|
|`Tractor Reassignment`|The current tractor is being replaced with another tractor.|
|`Trailer Reassignment`|The current trailer is being replaced with another trailer.|
|`At Drop Off`|The driver has arrived at the delivery location and is ready to unload the cargo.|
|`Unloading`|The cargo is being unloaded from the truck.|
|`Complete`|The delivery has been completed successfully.|
|`Delayed`|The load is delayed due to unforeseen circumstances.|
|`Cancelled`|The load has been cancelled and will not be delivered.|
|`Rescheduled`|The delivery has been rescheduled to a different time or date.|
|`Customs Hold`|The load is on hold due to customs clearance issues.|
|`Weather Delay`|The load is delayed due to adverse weather conditions.|
|`Accident`|The truck has been involved in an accident.|
|`Maintenance`|The truck is undergoing maintenance.|
|`Load Rejected`|The load has been rejected by the receiver.|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_load_log_id`|`primary key`|Primary key constraint|`load_log_id`|
|`fk_load_log_load_id`|`foreign key`|Foreign key constraint|`fk_load_id`|
|`fk_load_log_load_stop_id`|`foreign key`|Foreign key constraint|`fk_load_stop_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`load_stop`](./load-stop-table.md)|Many is to One|
|[`load`](./load-table.md)|Many is to One|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
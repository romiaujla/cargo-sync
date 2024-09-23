[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `service_center_specialty`

## Description

The `service_center_specialty` table stores information about the various specialties provided by service centers. Each record in this table represents a specific type of service that a service center can offer, such as engine repair, tire service, or emergency roadside assistance. This table is essential for categorizing and managing the different services available, ensuring that service centers can efficiently track and provide the necessary services to their clients.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`service_center_specialty_id`|Primary key|`integer`|❌||
|`fk_service_center_id`|Foreign key referencing the `service_center` table.|`integer`|❌||
|[`specialty`](#specialty)|Type of specialty provided by the service center.|`varchar(255)`|❌||
|`specialty_other`|When other is specified this will service as the description for other|`varchar(255)`|✓|`null`|
|&nbsp;|
|`created_at`|Timestamp when the record was created.|`timestamp`|❌|`current_timestamp`|
|`created_by`|ID of the user who created the record.|`integer`|❌|-1|
|`updated_at`|Timestamp when the record was last updated.|`timestamp`|❌|`current_timestamp`|
|`updated_by`|ID of the user who last updated the record.|`integer`|❌|-1|
|`deleted_at`|Timestamp when the record was deleted.|`timestamp`|✓|`null`|
|`deleted_by`|ID of the user who deleted the record.|`integer`|✓|`null`|

## Enums

### `specialty`

|Value|Description|
|-|-|
|`Alignment Service`|Wheel alignment services.|
|`Battery Replacement`| Testing and replacement of vehicle batteries.|
|`Brake Service`|Brake inspection and repair services.|
|`Diagnostics`| Comprehensive diagnostics for various vehicle systems.|
|`Electrical Systems`|Electrical systems diagnostics and repair.|
|`Emergency Roadside Assistance`|24/7 emergency roadside assistance.|
|`Engine Repair`|Engine repair services for semi trucks and trailers.|
|`Exhaust System Repair`| Repair and replacement of exhaust system components.|
|`Fuel System Service`| Cleaning and maintenance of the fuel system.|
|`Glass Repair`| Repair and replacement of vehicle glass, including windshields.|
|`HVAC Service`|Heating, ventilation, and air conditioning services.|
|`Inspection Services`| State and federal inspection services for compliance.|
|`Oil Change`| Regular oil change services to maintain engine health.|
|`Other`|Other specialty services not listed.|
|`Paint`|Painting services for semi trucks and trailers.|
|`Preventative Maintenance`|Scheduled preventive maintenance services.|
|`Suspension Repair`| Repair and maintenance of vehicle suspension systems.|
|`Tire Service`|Tire replacement and repair services.|
|`Trailer Repair`|General trailer repair services.|
|`Transmission Repair`|Transmission repair services for semi trucks and trailers.|
|`Truck Decals`|Application of truck decals and graphics.|
|`Upholstery Repair`| Repair and maintenance of vehicle interiors and upholstery.|
|`Wash`|Washing and cleaning services for semi trucks and trailers.|
|`Wheel Balancing`|Wheel balancing services.|




## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_service_center_specialty_id`|`primary key`|Primary key constraint|`service_center_specialty_id`|
|`fk_service_center_specialty_service_center_id`|`foreign key`|Foreign key constraint|`fk_service_center_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|[`service_center`](./service-center-table.md)|Many-to-One|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
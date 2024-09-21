[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `file`

## Description

The `file` table stores metadata about various files associated with loads, companies, and brokers. It includes information such as file type, subtype, visibility, and timestamps for creation, updates, and deletions. This table helps in organizing and managing files efficiently within the system.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`file_id`|Primary key|`integer`|❌||
|`key`|Unique key for the file|`varchar(255)`|❌||
|`mimetype`|MIME type of the file|`varchar(100)`|❌||
|`name`|Name of the file|`varchar(255)`|❌||
|`description`|Description for the file|`text`|✓|`null`|
|[`type`](#type)|Type of the file|`varchar(100)`|❌||
|[`sub_type`](#sub_type)|Sub Type of the file|`varchar(100)`|❌||
|`is_public`|Is the file public|boolean|❌|`false`|
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
|[`Load`](#load)|A file that is related to the load|
|[`Company`](#company)|Files associated to the company|
|[`Broker`](#broker)|Files associated to a broker|

### `sub_type`

#### `Load`

|Value|Description|
|-|-|
|`Load Confirmation`|Documents sent by brokers or shippers to confirm load details|
|`Bill of Lading (BOL)`|Detailed documents issued by a carrier that acknowledge receipt of cargo for shipment.|
|`Proof Of Delivery (POD)`|Documents signed by the consignee confirming the delivery of goods.|

#### `Company`

|Value|Description|
|-|-|
|`FMCSA Registration Documents`|Files required for the company’s registration with the Federal Motor Carrier Safety Administration.|
|`Environmental Compliance Files`|Documents ensuring compliance with emissions standards and environmental regulations.|
|`W-9`|Request for Taxpayer Identification Number and Certifications|
|`MC Authority Certificate`|Certificate of evidence that the carrier is authorized to engage in transportation as a common carrier of property by motor vehicle in interstate or foreign commerce|
|`Certificate of Liability Insurance`|Insurance certificate|

#### `Broker`

|Value|Description|
|-|-|
|`Broker Contracts and Agreements`|Legal documents outlining terms and conditions with freight brokers.|

## Constraints

|Constraint Name|Type|Description|Column(s)|
|--|--|--|--|
|`pk_file_id`|`primary key`|Primary key constraint|`file_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|None|

## Relationships

|Table Name|Relation*|
|-|-|
|None|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
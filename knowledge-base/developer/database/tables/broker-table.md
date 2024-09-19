[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `broker`

## Description

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`broker_id`|Primary key|`integer`|❌||
|`broker_name`|Name of the Broker|`varchar(255)`|❌||
|`doing_business_as`|If the Broker operates under a different name.|`varchar(255)`|✓|`null`|
|`motor_carrier_number`|Motor Carrier Number provided by the FMCSA, for companies registered with FMCSA.|`integer`|✓|`null`|
|`dot_number`|Department of Transportation (DOT) Number, i.e. required for interstate commerce in the USA.|`integer`|✓|`null`|
|`scac_code`|Standard Carrier Alpha Code (SCAC), it is a unique code for transportation companies.|`varchar(255)`|✓|`null`|
|`ein`|Employer Identification Number, also called Tax identification number for businesses.|`varchar(255)`|❌|
|`phone`|Broker phone number|`varchar(20)`|❌||
|`email`|Broker email|`varchar(255)`|❌||
|`website`|Broker website|`varchar(255)`|✓|`null`|
|`address`|Broker address field|`varchar(255)`|✓|`null`|
|`address_2`|Broker address line 2 field|`varchar(255)`|✓|`null`|
|`city`|Broker city field|`varchar(255)`|✓|`null`|
|`state`|Broker state field|`varchar(50)`|✓|`null`|
|`zip`|Broker zip field|`varchar(10)`|✓|`null`|
|`country`|Broker country field|`varchar(100)`|✓|`null`|
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
|`pk_broker_id`|`primary key`|Primary key constraint|`broker_id`|

## Indexes

|Index Name|Description|Column(s)|
|-|-|-|
|`idx_broker_username`|Index description|`username`|

## Relationships

|Table Name|Relation*|
|-|-|
|[`broker_note`](./broker-note-table.md)|One is to many|


<span style="font-size:10px">\* Relational directions mentioned in the table above are from the current table to other table</span>
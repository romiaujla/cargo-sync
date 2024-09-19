[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `role`

## Description
Represents the Role table in the database. The Role table is used to store information about different roles that can be assigned to users within the application. Each role defines a set of permissions and access levels that determine what actions a user can perform.

## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`role_id`|Primary key|`integer`|❌||
|`role_name`|Name of the role|`varchar(255)`|❌||
|`description`|Description of the role|`varchar(255)`|✓||
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
|`pk_role_id`|`primary key`|Primary key constraint|`role_id`|
|`unique_role_name`|`unique`|Ensures that each role name is unique|`role_name`|

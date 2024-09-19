[← Cargo Sync Documentation](../../../../readme.md) [← Developer Knowledge Base](../../readme.md) [← Database Table List](../database-design.md)

# `note`

## Description
The `note` table is designed to store all user-generated notes within the application. These notes can be associated with various resources, including users, loads, locations, and other entities. This table ensures that each note is uniquely identifiable and maintains comprehensive metadata about its creation, updates, and deletion. By linking notes to different resources, the application can provide a rich and interconnected user experience, facilitating better data organization and retrieval.


## Columns

|Column Name|Description|Data Type|Nullable|Default|
|-|-|-|-|-|
|`note_id`|Primary key|`integer`|❌||
|`content`|Content of the note|`text`|❌||
|`pinned`|Indicates if the note is pinned|`boolean`|❌|`false`|
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
|--|--|--|--|
|`pk_note_id`|`primary key`|Primary key constraint|`note_id`|

## Indexes

None

## Relationships

|Table Name|Relation (`note : user_note`)|
|-|-|
|[`user_note`]|One is to many|

### Table of Contents
- [User Stories](#user-stories)
    - [User Management](#user-management)
    - [Load Management](#load-management)
        - [Load Scenarios](#load-scenarios)
            - [Happy Path](#happy-path)
    - [Pick Up/Delivery Location Management](#pick-updelivery-location-management)
- [SQL DDL](#sql-ddl)

### User Stories

#### User Management
- TBD

#### Load Management
- Have one table for Loads
- Load goes from pick up to delivery
- One load can have multiple pick up locations
- One load can have multiple delivery locations

##### Load Scenarios
###### Happy Path
- 1 Pick Up - 1 Delivery
- Load goes thru the following statuses
        - Headed to Pick Up
        - Arrived On Time To Pick up
        - Loading
        - Loaded
        - Headed to Delivery
        - Arrived On Time To Delivery
        - Unloading
        - Unloaded


#### Pick Up/Delivery Location Management
- Have one table for pick up and one table for delivery locations
- TBC...

### SQL DDL
> [https://drawsql.app/teams/self-573/diagrams/transportationmanagement](https://drawsql.app/teams/self-573/diagrams/transportationmanagement)

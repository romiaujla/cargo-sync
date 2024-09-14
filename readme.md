
### Table of Contents
- [User Stories](#user-stories)
    - [User Management](#user-management)
    - [Load Management](#load-management)
        - [Load Stages](#load-stages)
            - [Load Created / Scheduled](#load-created--scheduled)
            - [Load Confirmed](#load-confirmed)
            - [Truck Dispatched](#truck-dispatched)
            - [At Pick-Up Location](#at-pick-up-location)
            - [Loading in Progress](#loading-in-progress)
            - [Load Picked Up](#load-picked-up)
            - [In Transit](#in-transit)
            - [At Delivery Location](#at-delivery-location)
            - [Unloading in Progress](#unloading-in-progress)
            - [Load Delivered](#load-delivered)
            - [Load Completed](#load-completed)
            - [Load Delayed](#load-delayed)
            - [Load Canceled](#load-canceled)
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

##### Load Stages
###### Load Created / Scheduled
> Scenario: The shipper schedules a load for pick-up
>
> Details: All necessary information about the load (pick-up/delivery location, weight, type of cargo, etc.) is entered into the system, and the shipment is assigned to a driver/truck.

###### Load Confirmed
> Scenario: The carrier confirms the assignment.
>
> Details: Once the driver accepts the assignment, the load is confirmed for pick-up.

###### Truck Dispatched
> Scenario: The truck is dispatched to the pick-up location.
>
> Details: The driver receives instructions, and the system updates the load status to show that the truck is en route to the pick-up.

###### At Pick-Up Location
> Scenario: The driver arrives at the pick-up location.
>
> Details: The system tracks the driver’s arrival at the origin location.

###### Loading in Progress
> Scenario: Cargo is being loaded onto the truck.
>
> Details: The load status is updated to show the loading process, with potential for real-time updates (e.g., 50% loaded).

###### Load Picked Up
> Scenario: Cargo is successfully loaded, and the driver departs.
>
> Details: The load status changes to "In Transit" with the estimated time of arrival (ETA) at the delivery destination.

###### In Transit
> Scenario: The truck is en route to the delivery destination.
>
> Details: The system tracks the location of the truck in real-time (if using GPS) and provides updates on estimated delivery time.

###### At Delivery Location
> Scenario: The driver arrives at the delivery point.
>
> Details: The system updates the status to reflect the driver’s arrival at the destination.

###### Unloading in Progress
> Scenario: The cargo is being unloaded.
>
> Details: Similar to the loading phase, the system shows the progress of the unloading process.

###### Load Delivered
> Scenario: The cargo is fully delivered and handed over to the recipient.
>
> Details: The load status is updated to "Delivered," and proof of delivery (POD) is captured, either via electronic signature or other documentation.

###### Load Completed
> Scenario: All processes related to the delivery, such as paperwork and payments, are finalized.
>
> Details: The load is officially marked as completed, and records are updated in the system.

###### Load Delayed
> Scenario: If the driver faces delays, such as traffic or mechanical issues, this status can update the load.

###### Load Canceled
> Scenario: In case the load is canceled before pick-up or in transit, the system can update the status to reflect this.

### Pick Up/Delivery Location Management
- TBD

### SQL DDL
> [https://drawsql.app/teams/self-573/diagrams/transportationmanagement](https://drawsql.app/teams/self-573/diagrams/transportationmanagement)

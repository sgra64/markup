<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
# Requirements Document for *Freerider.de*

This document provides the *specifications of requriements* (use cases) for
the *freerider.de* car sharing system.
The document follows a structure:

1. [*System Overview*](#1-system-overview)

1. [*Stakeholders*](#2-stakeholders)

1. [*Actors & Roles*](#3-actors--roles)

1. [*Use Case Index*](#4-use-case-index)

1. [*Detailed Use Cases*](#5-detailed-use-cases)


&nbsp;

## 1. System Overview

*Freerider.de* is a *Car-Rental-System (CRS)* system
that manages a fleet of cars mainly in cities without permanent stations.
Cars are parked in public spaces when not used. Customer can reserve vehicles
at particular times and locations. Car pick-up and return are fully handled
over customer mobile phones. Staff (Rental agents) are only involved in cases
of technical problems, damage, theft or traffic accidents.


&nbsp;

## 2. Stakeholders

This section names *stakeholders* as individuals, groups, or organizations
involved in decision making, investment or oversigh, but who are not primary
users of the system.

| Stakeholder                  | Description |
| :---                         | :---        |
| *Owner*                      | owner of *freerider.de*.                       |
| *CEO*                        | executive manager of *freerider.de*.           |
| *Investors*                  | holders of financial stakes in *freerider.de*. |
| *Authorities (City Council)* | oversight granting permission to operate *freerider.de*. |
| *Product Owner (PO)*         | defines product features and delivery timelines; acts as a bridge between stakeholders, customers, and the development team. |


&nbsp;

## 3. Actors & Roles

This section names *actors* and *roles* representing users and anything that
interacs with a system. *Primary actors* represent targeted user groups
while *Secondary actors* represent entities needed for operation.

| Actor/Role              | Type      | Description |
| :---                    | :---      | :---        |
| *Guest*                 | Primary   | role of an unregistered user who can explore offers. |
| *Customer (individual)* | Primary   | registered person with validated information (name, address, contact, payment  |information).
| *Customer (business)*   | Primary   | registered business entity with validated information, specifically a tax-id  |(Umsatzsteuernummer).
| *Customer (driver)*     | Primary   | person with validated driver's license. |
| *Staff*                 | Primary   | employee of *freerider.de*. |
| *Service Agent*         | Primary   | staff member who handles exception cases such as damage, theft or accidents. |
| *Fleet Manager*         | Secondary | staff member who manages the fleet of vehices, e.g. on-boards and off-boards vehicles. |
| *Vehicle*               | Primary   | actor that creates pickup and return reports in each vehice and sends them to (interacts  |with) the system.
| *Payment Service*       | Secondary | actor that handles payments and interacts with the system. |


<!-- | **Fleet Manager** | Primary | Manages vehicle inventory, maintenance schedules, and pricing rates. | -->
<!-- | **DMV / Verification Service** | External System | Verifies driver's license validity and driving history (optional integration). | -->
<!-- | **System Administrator** | Primary | Manages user accounts, roles, system parameters, and system logs. | -->


&nbsp;

## 4. Use Case Index

This section names all Use Cases included in Section 5:

- **UC-100:** *Reserve a Vehicle*
- **UC-110:** *Manage Reservation (Modify)*
- **UC-120:** *Manage Reservation (Cancel)*
- **UC-200:** *Vehicle Pickup*
- **UC-210:** *Create Pickup Report*
- **UC-300:** *Vehicle Return*
- **UC-310:** *Create Return Report*
- **UC-400:** *Register new Customer*
- **UC-410:** *Unregister Customer*
- **UC-500:** *Manage Fleet Inventory*
- **UC-550:** *Permanently send GPS-location*

<!-- 
| UC-ID  | Description |
| :---   | :---        |
| UC-100 | *Reserve a Vehicle*             |
| UC-110 | *Manage Reservation (Modify)*   |
| UC-120 | *Manage Reservation (Cancel)*   |
| UC-200 | *Vehicle Pickup*                |
| UC-210 | *Create Pickup Report*          |
| UC-300 | *Vehicle Return*                |
| UC-310 | *Create Return Report*          |
| UC-400 | *Register new Customer*         |
| UC-410 | *Unregister Customer*           |
| UC-500 | *Manage Fleet Inventory*        |
| UC-550 | *Permanently send GPS-location* |
-->


&nbsp;

## 5. Detailed Use Cases

This section contains detailed descriptions of use cases, each following the
same template:
[UC-CRS-template.docx](UC-CRS-template.docx) /
[UC-CRS-template.pdf](UC-CRS-template.pdf).


### Use Case UC-100: *Reserve a Vehicle*

This use case describes when a *Customer* wants to reserve a vehicle of a
desired class, time of use and desired pickup and return locations.
Payment is required for a successful reservation.

The use case description includes:

* Primary Actor: *Customer*
* Secondary Actors: *System*, *Payment Provider*

<!-- 
* *Section 1* describes conditions that trigger of the use case.
 -->

* *Section 1* states the goal of the use case.

* *Section 2* lists pre- and post-conditions as statements that hold (are true)
    before and after the use case.

<img src="img/UC-CRS-UC100 Create Reservation-1.png" width="600"/>

<!-- 
* **Primary Actor:** Customer

* **Secondary Actors:** System, Payment Provider

* **1. Goal:** Allow a customer to search, select, and book a vehicle of a selected
class for a specified timeframe and pickup and return locations.


* **2. Pre-conditions:** 

  1. Customer is “active” (permitted to perform business operations).


* **Post-conditions:** 

  1. A reservation record is created with a status of `CONFIRMED`.

  2. Inventory availability is updated (vehicle held/allocated).

  3. A confirmation email/SMS is sent to the customer.
 -->


&nbsp;

#### 3. Main Success Scenario (*"Happy Path"*):

This section describes steps the primary actor must perform in order to
achieve the goal of the use case. Only the *"Happy Path"* is considered.
Errors are described in section 

<img src="img/UC-CRS-UC100 Create Reservation-2.png" width="600"/>


&nbsp;

#### 4. Error Paths and Exception Flows:

This section describes errors that may occur when the use case is performed.

<img src="img/UC-CRS-UC100 Create Reservation-3.png" width="600"/>


---

### Use Case UC-120: *Manage Reservation (Cancel)*

```
...
```


---

### Use Case UC-200: *Vehicle Pickup*

```
...
```


---

### Use Case UC-210: *Create Pickup Report*

```
...
```

---

### Use Case UC-300: *Vehicle Return*

```
...
```


---

### Use Case UC-310:** *Create Return Report*

```
...
```


---

### Use Case UC-400:** *Register new Customer*

```
...
```


---

### Use Case UC-410:** *Unregister Customer*

```
...
```


---

### Use Case UC-500:** *Manage Fleet Inventory*

```
...
```


---

### Use Case UC-550:** *Permanently send GPS-location*

```
...
```


---

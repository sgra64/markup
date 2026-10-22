<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
<!-- 
Gemini: Can you give me a fully written-out use case document for a car rental system a markdown document?
 -->

# Use Case Specification Document: Car-Rental-System *Freerider.de*

## 1. System Overview

**Freerider.de** is a *Car-Rental-System (CRS)* with an integrated web and
mobile platform that allows customers to search for, reserve, modify, and pay
for rental vehicles. It also provides fleet management, billing, and reporting
tools for agency staff and administrators.

---

## 2. Actors & Roles

| Actor | Type | Description |
| :--- | :--- | :--- |
| **Guest (Unregistered)** | Primary | Browses inventory, can register. |
| **Customer (Registered)** | Primary | Browses inventory, books reservations, manages profile, and processes payments. |
| **Rental Agent** | Primary | Handles vehicle pickup/return processes, verifies documentation, and inspects vehicles. |
| **Car** | Primary | Creates pick-up and return report. Sends the report to the system and also GPS-location data every 5 minutes. |
<!-- | **Fleet Manager** | Primary | Manages vehicle inventory, maintenance schedules, and pricing rates. | -->
| **System Administrator** | Primary | Manages user accounts, roles, system parameters, and system logs. |
| **Payment Gateway** | External System | Processes credit/debit card transactions and refunds securely. |
| **DMV / Verification Service** | External System | Verifies driver's license validity and driving history (optional integration). |


---

## 3. Use Case Index

The section of the Use Case Index lists all use cases of the Use Case Document:

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


---

## 4. Detailed Use Cases

### Use Case UC-100: *Reserve a Vehicle*

* **Primary Actor:** Customer

* **Secondary Actors:** System, Payment Provider

* **Goal:** Allow a customer to search, select, and book a vehicle of a selected
class for a specified timeframe and pickup and return locations.


* **Pre-conditions:** 

  1. Vehicles of the requested class are available at desired locations.


* **Post-conditions:** 

  1. A reservation record is created with a status of `CONFIRMED`.

  2. Inventory availability is updated (vehicle held/allocated).

  3. A confirmation email/SMS is sent to the customer.


#### Main Success Scenario (MSS):

1. Customer browses catalog of vehicles and map of locations.

1. Customer enters or selects specific dates, times, pickup/drop-off locations and the desired vehicle category.

1. Customer sends this information as inquiry to the system.

1. The system verifies the inquiry and responds to the customer with

    a. accepting the inquiry and offering a final price or

    b. returning a close match to the inquiry, also with a final price or

    c. returning that the inquiry cannot be met.

1. The customer has 10 minutes to

    a. accept the offer or

    b. reject the offer or not to respond.

1. If the customer has accepted the offer, payment must be made by:

    a. entering payment information or

    b. selecting a authorized payment method registered in the customer's profile.

1. In case of new payment information, the payment information must be validated
    with the payment provider in order to be accepted.

    a. Payment is requested from the payment provider.

1. In case of existing payment information (e.g. a registered credit card that has
    already been used), the payment is immediately requested from the payment provider.

1. The system sends a confirmation to the customer.

<!-- 
6. Customer inputs driver details (Name, Contact, Driver’s License Number) or logs into an existing account.
7. System calculates final price including taxes, fees, and selected options.
8. Customer enters payment information.
9. System contacts Payment Gateway to authorize payment or place a hold.
10. Payment Gateway confirms authorization.
11. System creates the reservation, assigns a unique Reservation ID, updates vehicle availability, and displays the receipt to the Customer.
 -->


#### Extensions (alternative paths):

**4c. No vehicles available for selected dates/location:**

- 4c.1 System notifies the customer of no availability.

- 4c.2 System suggests alternative nearby pickup locations or alternative dates.

- 4c.3 Customer updates search parameters or exits.


**7a. Payment authorization fails (e.g., invalid card):**

- 7a.1 System notifies the customer of the payment failure.

- 7a.2 System prompts customer to re-enter payment details or try a different card.

- 7a.3 Customer provides valid payment or cancels reservation process.


**8. Payment fails within 12 hours after accepting a reservation (e.g., insufficient funds):**

- 8.1 System notifies the customer of the payment failure.

- 8.2 System reverts the status of the reservation from `CONFIRMED` to `PENDING` with
    note `failed payment`.

- 8.3 System notifies the customer to enter new payment information, e.g. of a different card.

- 8.4 Customer provides valid payment or cancels reservation process.

    a. System reverts the status of the reservation from `PENDING` to `CANCELLED` when the customer cancells the reservation.

- 8.5 System reverts the status of the reservation from `PENDING` to `CONFIRMED` and
    removes the note `failed payment` when payment arrives within a renewed 12h timeframe.

- 8.6 System reverts the status of the reservation from `PENDING` to `CANCELLED` when
    no payment has arrived within another 12h timeframe.

    a. System notifies the customer about the cancellation.


---

### UC-110: *Manage Reservation (Modify)*

* **Primary Actor:** *name an actor*

* **Secondary Actors:** *name secondary actors, if any*

* **Goal:** *formulate a sentence for the main goal of the use case.*

* **Pre-conditions:**
  1. *name pre-conditions for the use case, if any*

* **Post-conditions:** 
  1. *name post-conditions for the use case, if any*

#### Main Success Scenario (MSS):
*Describe steps of the use case for the success scenario.*

#### Extensions (alternative paths):
*Describe other possible paths that are not part of the main success scenario.*


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

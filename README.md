<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B1-B6: *Requirements Analysis* -- *What* does the *User* want?

*Requirements* are formalized (written) and with all stakeholders agreed
*expectations* of a (software) product. *Requirements* need to be clarified
*before* software development starts.

The goal of *Requirements Analysis* is:

1. to collect ideas and proposals from all stakeholders.

1. to summarize and rationalize ideas and proposals and organize them in a
    common structure.

1. to deepen the understanding of interactions and processes by all stakeholders
    *before* software development begins.

1. to develop a unified (domain) terminology that is accepted by all stakeholders
    ([*Glossary*](GLOSSARY.md)).

1. to derive concrete specifications of *what* to build for a system.

*Requirements Analysis* is a commuication-intensive process aimed at clarifying
*what* a software system is expected to do, not *how* it is going to achieve it.

Audience of *Requirements Analysis* are stakeholders (people), hence *quality*
and (human-consumable) *quantity* of produced material matters.


&nbsp;

*Requirements Analysis* considers two perspectives:

- the *user's perspective* reflects what user's expect of a software
    product and how they would interact with it.

    - Techniques used are: *Use Cases* (task B1), *UML Use Case Diagram*
        (task B2) and *User Stories* (task B3).

- the *systems's perspective* describes which functions the system must
    provide in order to fullfill user's expectations, including non-functional
    aspects in terms of *quality*, *quantity*, *usability*, *security*,
    *time lines*, *economic* and other factors.

    - Techniques used are the specificationn of *Functional Requirements (FR)*
        and *Non-functional Requirements (NFR)* (task B4).

[*Acceptance criteria*](https://www.atlassian.com/work-management/project-management/acceptance-criteria)
specify concrete criteria defined by a
[*Product Owner*](https://www.atlassian.com/agile/product-management/product-owner)
role in order to validate that a requirement (a *Use Case*, a *User Story* or just a *feature*)
has been implemented. Sometimes, a term
[*"Definition-of-Done"*](https://www.atlassian.com/agile/project-management/definition-of-done)
(*DoD*) is also used.


&nbsp;
---
### *Context / Scenario*

*freerider.de* is a car rental / car sharing company that operates a fleet of
cars mainly in cities without permanent stations. Cars are parked in public
spaces when not used. The system permanently tracks car locations by GPS.
Vehicle can be reserved at particular times and locations.
If a reservation is accepted, the vehicle will be made available at the
requested time and location.

Customers can search a catalog of cars (small, mid, large sedan, convertible,
SUV, etc.) and *select* a destination to pick-up and return (drop) the vehicle
at desired times. Then, the customer sends an *inquiry* with the selection to
the system asking to price and confirm the reservation. The system answers the
inquiry with an *offer*, including the final price, or suggests a close match,
if the inquiry cannot fully be met. The system holds the offer for 10 minutes,
within which the the customer can accept or reject the offer. If accepted,
payment is required to finalize the *reservation*.

Changes to reservations (times, locations, car-class) or cancellations can
be requested by a cutsomer and need to be approved by the system. If they
cause price changes (e.g. for a different car class), they need approval by
the customer.
Changes or cancellations initiated by *freerider.de* are communicated to the
customer with a proposed alternative or compensation. The customer decides
which option to choose.

When the customer approaches the vehicle at the time of pickup, he requests
*freerider.de* to open the vehicle from his mobile phone. The system verifies
the reservation and requests the customer presenting a valid driver's license
of him or herself or of the driver who is going to drive the car. The driver's
license is presented to the mobile phone's camera. The system may ask to also
make a photo of the driver in order to validate the license. If the license
is recognized, the system opens the car.
At this time, the car creates the pick-up report of the car's condition with
km, fuel level, GPS-location and other technical data. The customer can inspect
the report on his mobile phone, add comments and photos. The car is ready
for use.

For returning the car, the customer sends a return-requests from his phone.
The system then initiates the car to create the return-report with km, fuel
level, GPS-location and other technical data. The customer can open the report,
add comments and photos. When the customer closes the door, the car is locked.

Car pick-up and return are fully handled remotely by the system. In case of
technical problems, damage, theft or traffic accidents, the customer notifies
*freerider.de* and a service agent (staff) will handle the case with full access
to all documents.


&nbsp;

**Tasks:**

Understand the car rental scenario and complete tasks:

- [*B1: Use Cases, Glossar*](README-B1-Use-Cases-Glossary.md), 4 Pkt.

- [*B2: UML Use Case Diagram*](README-B2-Use-Case-Diagram.md), 4 Pkt.

- [*B3: User Stories*](README-B3-User-Stories.md), 3 Pkt.

- [*B4: Functional and Non-functional Rquirements*](README-B4-FA-NFA.md), 3 Pkt.

- [*B5: Business Process: New Customer Registration (individual)*](README-B5-BP-Registration.md), 5 Pkt.

- [*B6: Business Process: Car Reservation*](README-B6-BP-Reservation.md), 5 Pkt.


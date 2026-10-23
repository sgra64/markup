<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B1-B4: *Requirements Analysis* -- *What* does the *User* want?

*Requirements* are formalized (written) and with all stakeholder agreed
*expectations* of a software product *before* software development starts.

The goal of *Requirements Analysis* is:

1. to collect ideas and proposals from all stakeholders.

1. to summarize and rationalize ideas and proposals and organize them in a
    common structure.

1. to deepen the understanding of interactions and processes by all stakeholders
    *before* software development begins.

1. to develop a unified (domain) terminology that is accepted by all stakeholders
    (glossary).

1. to derive concrete specifications of a system to build.

*Requirements Analysis* is a commuication-intensive process aimed at clarifying
*what* a software system should do, not *how* it does it.

Audience of *Requirements Analysis* are people, hence *quality* and *quantity*
of produced material matters. *Artificial Intelligence* can help to summarize and
rationalize content and to find contradictions and errors.


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
If a customer wishes a vehicle at a particular time at a particular location,
*freerider.de* will make a car available with an existing reservation.

Customers can search a catalog of cars and destinations to pick-up and return
(drop) vehicles at desired time-frames. The customer can create an inquiry for
a vehicle of a certain class (small, mid, large sedan, convertible, SUV, etc.),
at a specific location at a desired time for a desired period and send this
inquiry to the system. The system answers the inquiry with an offer, including
price, or suggests a close match, if the inquiry cannot fully be met. The
system holds the offer for 10 minutes, within which the the customer can accept
the reservation or reject. Payment is required to to finalize a reservation.

Reservation changes (time, car-class, cancellation) must be requested by the
customer and need to be approved by the system. Changes initiated by
*freerider.de* are communicated to the customer with a proposed alternative
or compensation. The customer decides which option to choose.

When the time of pickup has arrived, the customer approaches the vehicle and
requests to open from his mobile phone. The system verifies the reservation and
opens the car if valid. A report of the car's condition is prepared by the car
with km, fuel level (gas, battery), GPS-location and technical data. The customer
can inspect the report on his phone, add comments and photos. The car is ready
for use.

When returning the car, the customer requests the return on his phone. The
system then initiates that a return-report is created by the car, again with
km, fuel level, GPS-location and technical data. The customer can open the
report, add a comment and photos. When the customer closes the door, the
car is locked.

Car pick-up and return are fully handled by the system. In case of a problem
or a traffic accident, a rental agent (staff member) is contacted to handle
the case with full access to all documents.

Car pick-up and return are fully handled over customer mobile phones. Staff
(Rental agents) are only involved in cases of technical problems, damage,
theft or traffic accidents.


&nbsp;

**Tasks:**

Understand the car rental scenario and complete tasks:

- [*B1: Use Cases, Glossar*](README-B1.md), 4 Pkt.

- [*B2: UML Use Case Diagram*](README-B2.md), 4 Pkt.

- [*B3: User Stories*](README-B3.md), 3 Pkt.

- [*B4: Functional and Non-functional Rquirements*](README-B4.md), 3 Pkt.

- [*B5: Business Process: New Customer Registration*](README-B5.md), 5 Pkt.

- [*B6: Business Process: Car Reservation*](README-B6.md), 5 Pkt.


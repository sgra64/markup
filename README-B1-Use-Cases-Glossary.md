<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B1: *Use Cases*

[*Use Cases*](https://en.wikipedia.org/wiki/Use_case) describe specific steps,
actions and interactions between a user (an actor) and a software system.

Specifying *Use Cases* is part of
[*Requirement Analysis*](https://en.wikipedia.org/wiki/Requirements_analysis)
in [*Software Engineering*](https://en.wikipedia.org/wiki/Software_engineering).

*Use Cases* can be specified in different forms:

1. as detailed descriptions (*"Use Case Document"*),

1. visually as an [*UML-Use Case Diagram*](https://de.wikipedia.org/wiki/Anwendungsfalldiagramm),

1. as [*User Stories*](https://en.wikipedia.org/wiki/User_story).

1. A *Glossary* includes a list of short explanations of terms that are
    relevant in the context of the scenario.


A *"Use Case Document"* is a classic form of describing use cases following
a certain structure (schema).

In this section, requirements for the scenario are analyzed in form of a
use cases document [*UC-CRS.md*](UC-CRS.md) that follows the structure with
sections:


#### 1. **System Overview:**

*Freerider.de* is a *Car-Rental-System (CRS)* system
that manages a fleet of cars mainly in cities without permanent stations.
Cars are parked in public spaces when not used. Customer can reserve vehicles
at particular times and locations. Car pick-up and return are fully handled
over customer mobile phones. Staff (Rental agents) are only involved in cases
of technical problems, damage, theft or traffic accidents.

#### 2. Stakeholders

This section names *stakeholders* as individuals, groups, or organizations
involved in decision making, investment or oversigh, but who are not primary
users of the system.

#### 3. Actors & Roles

This section names *actors* and *roles* representing users and anything that
interacs with a system. *Primary actors* represent targeted user groups
while *Secondary actors* represent entities needed for operation.

#### 4. **Use Case Index**

This section lists the use cases included in the document.

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
- ...

#### 5. Detailed Use Cases

This section contains detailed descriptions of use cases, each following the
same template:
[UC-CRS-template.docx](UC-CRS-template.docx) /
[UC-CRS-template.pdf](UC-CRS-template.pdf).


&nbsp;

---

**Tasks:** Understand the [*vehicle reservation scenario*](Scenario_EN.md).

Understand the description of use case *UC-100: *Reserve a Vehicle* in document
[*UC-CRS.md*](UC-CRS.md).


*Task 1:*

Answer questions:

1. What is a *stakeholder* in requirement engineering?

1. What is an *actor* in requirement engineering?

1. Name three *stake holders* in the scenario and three *actors*.


&nbsp;

*Task 2:*

Choose three (3) use cases from the list above and complete them following
the same template:
[UC-CRS-template.docx](UC-CRS-template.docx) /
[UC-CRS-template.pdf](UC-CRS-template.pdf).

Choose one use case from the *100's* (except *UC-100*), one from the *200's*,
one from the *400's* categories and complete them.

Name at *least one* pre-condition and *at least one* post-condition
in section 2.

For section 3, describe steps for the *success scenario* *("Happy Path")*
of the use case and describe *at least one* error path.

You may print and use templates.


&nbsp;

*Task 3:*

Add five more use cases (only name the *ID* and *title*) to the section with
the *Use Case Index*.

<!-- 
add 5 more use cases:
- UC-130 Transfer Reservation to other Customer

- UC-202 Validate Driver's License at Pickup
- UC-203 Validate Driver's Soberness at Pickup

- UC-320 Report Damage at Return
- UC-321 Manage Damage Report (Modify)
- UC-322 Manage Damage Report (Cancel)
- UC-330 Dispute Damage Claim at Return

- UC-410 Unregister Customer (self)
- UC-411 Unregister Customer (by System)
-->


&nbsp;

*Task 4:*

Start a document named *"Glossary"* and include terms (words) of:

- 3 actors/roles that are using the system,

- 3 types of (data-) objects the system manages,

- 3 relevant (business-) activities / processes.

with short explanations of what these terms mean in the context of
the car reservation scenario.

Example:

```
Glossary:

- Back Office: actor that represents and coordinates activities on behalf of
    freerider.de, e.g. approves car reservation requests, new customers, etc.

- Vehicle: car, mini-bus or motorcycle a customer reserves and rents.

- Customer: ...

...
```

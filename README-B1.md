<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B1: *Use Cases* -- What does the *User* want?

[*Use Cases*](https://en.wikipedia.org/wiki/Use_case) describe what a user
expects of a software system or an application and how he/she
would interact with that system. Specifying *Use Cases* is part of
[*Requirement Analysis*](https://en.wikipedia.org/wiki/Requirements_analysis)
in [*Software Engineering*](https://en.wikipedia.org/wiki/Software_engineering).

*Use Cases* can be specified in different forms:

1. as detailed descriptions (*"Use Case Document"*),

1. visually as an [*UML-Use Case Diagram*](https://de.wikipedia.org/wiki/Anwendungsfalldiagramm),

1. as [*User Stories*](https://en.wikipedia.org/wiki/User_story).


A *"Use Case Document"* is a classic form of describing use cases following
a certain structure (schema).

In this section, requirements for the scenario are analyzed in form of a
use cases document [*UC-CRS.md*](UC-CRS.md) that follows the structure with
sections:

1. **System Overview:** *Freerider.de* is a *Car-Rental-System (CRS)* system
that manages a fleet of cars mainly in cities without permanent stations.
Cars are parked in public spaces when not used. Customer can reserve vehicles
at particular times and locations. Car pick-up and return are fully handled
over customer mobile phones. Staff (Rental agents) are only involved in cases
of technical problems, damage, theft or traffic accidents.

2. **Actors & Roles:**

This section names actors and roles that have use cases with the system.
<!-- *Guest (Unregistered)*, *Customer (Registered)*, *Rental Agent*,
*Fleet Manager*, *System Administrator*, *Payment Gateway*,
*DMV / Verification Service*. -->

3. **Use Case Index**

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


&nbsp;

**Task:** Understand the car rental scenarion. Understand the description of
use case *UC-01* in the document [*UC-CRS.md*](UC-CRS.md).

*Task 1:*

What is a *stake holder* in requirement engineering?

What is an *actor* in requirement engineering?

Name three *stake holders* in the scenario and three *actors*.


&nbsp;

*Task 2:*

Choose five use cases that have not been completed and complete them.
Choose one use case from the *100's*, one from the *200's*, one from the *300's*
categories and use cases *400* and *410*.

For each use case, name at *least one* pre-condition and *one* post-condition
and describe *at least one* alternative/error path.

Prepare use cases in *hand-writing* (machine-typed or AI-generated text is not
accepted). You may print and use [*UC-CRS-template.docx*](UC-CRS-template.docx) or
[*UC-CRS-template.pdf*](UC-CRS-template.pdf).


&nbsp;

*Task 3:*

Name five more use cases for the scenario (only *ID* and *title*).


&nbsp;

*Task 4:*

Start a document named *"Glossary"* and include terms (words) of:

- 3 actors/roles,

- 3 objects and

- 3 activities

with short explanations of what these terms mean in the context of
the car reservation scenario.

Example:

```
Glossary:
Vehicle: car, mini-bus or motorcycle a customer reserves and rents.
Customer: ...
...
...
...
```

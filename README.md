<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## C1-C5: *Design* -- *Vehicle-Reservation* System

While *Requirement Analysis* focuses on collecting and organizing requirements
of *what* is the system expected to do, *Design* focuses on creating specifications
for the system to build.

The *Design* of software systems is often divided into:

* **Logical Design** focsued on function, purpose (processing business data) and
    interactions (with *actors* and with other systems). *Logical Design*
    creates specifications (often using *UML-Diagrams*) of:

    1. the *Data Model* with *Entity Types* (*"Business Objects (BO)"*),
        *Relations* and *Cardinalities* using *UML-Class* or *ER-Diagrams*.

    1. the implementation of *Business Processes (BP)*, e.g. by means of
        defining *State Machines* for business objects using the
        *UML-Statechart Diagram*.

    1. *Components* of the system using the *UML-Component Diagram* -- in terms
        of *Services* and the internal structure of *Services*.

    1. *Interfaces (API)* of system components using a style (*REST*) and an
        *API-Specification* framework such as
        [*OpenAPI Specification*](https://swagger.io/specification/v3.2).

    1. *Interactions* (protocols) between components and with actors using the
        *UML-Sequence Diagram*.

* **Technical Design** focuses on describing the technical build-up needed to
    implement the *Logical Design* with:

    - *Machines* (servers, containers) *"on premise"* or in the cloud for
        hosting and running
        - *HTTP-access* (web/http-tier) instances (http servers),
        - *application instances* (running JVM and Java-Code) and
        - *database instances* hosting the databases used by the application.

    - *Network* build-out with *sub-nets* (public access, DMZ, internal), ports,
        connections (open ports), DNS-names (URL's), etc.

    - *Storage* with *volumes* residing in storage devices (e.g.
        *HPE Alletra Storage MP B10000*, [*spec*](https://www.hpe.com/psnow/doc/a50006985enw)
        or [*IBM Storage*](https://www.ibm.com/de-de/solutions/storage) with
        [*IBM FlashSystem*](https://www.ibm.com/de-de/products/flashsystem#specifications)
        with up to *11PB*).
        Alternatively, storage can also be aquired in the cloud (e.g. *HPE GreenLake*
        pay-as-you-go, managed cloud storage).


&nbsp;

- *Logical Design* focuses on the *"logic"* of the system

    - given by the *Functional Requirements (FR)*.

- *Technical Design* defines the non-functional properties of the system

    - given by *Non-Functional Requirements (NFR)*, main;y concerning the *"-ilities"*:

        - *Availability* - replication and fail-over measures (for servers and storage),

        - *Recoverability* - Backup- and Recovery-Strategy (BUR-Strategy),

        - *Scalability* - capabilities of vertical and horizontal build-out,

        - *Security* - firewalls and network zones,

        - *Data-protection* - management of roles and permission, access control
            (e.g. to databases), access logging, etc.


&nbsp;

**Tasks:**

Design tasks focus on *Vehicle-Reservation* and the design of the
*Vehicle-Reservation System*. The
[*Vehicle-Reservation - Process*]()
defines the intended behavior for handling vehicle reservations.

Steps:

- C1: [Design of the *Data Model* with *Entity-Types*](README-C1-Datamodel.md) - 3 Pkt -
    *Data Model* with *Entity Types* (*"Business Objects (BO)"*), *Relations*
    and *Cardinalities* using *UML-Class* or *ER-Diagrams*.

- C2: [Design of the Implementation of *Business Processes (BP)*](README-C2-business-processes.md) - 2 Pkt -
    the implementation of *Business Processes (BP)* by *State Machines*
    associated with business objects using the *UML-Statechart Diagram*.

- C3: [*Component* / *Services* Design](README-C3-services.md) - 2 Pkt -
    the design of system *Services* and the internal structure of
    *Services* using the *UML-Component Diagram*.

- C4: [*Interface (API)* Design](README-C4-interfaces.md) - 2 Pkt -
    the design of *Service* *Interfaces* *(API)* using *REST* and the
    [*OpenAPI Specification*](https://swagger.io/specification/v3.2).

- C5: [*Interactions*](README-C5-interactions.md) - 2 Pkt -
    the design of *Interactions* (protocols) between *Component* / *Services*
    using the *UML-Sequence Diagram*.

- C6: [Aspects of *Technical Design*](README-C6-technical-design.md) - 2 Pkt -
    aspects of *Technical Design* by understanding the build-out on
    a laptop.


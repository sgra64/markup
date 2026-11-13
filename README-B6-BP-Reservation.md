<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B6: Business Process: *Vehicle Reservation*


*Vehicle Reservation* is the central process for the *Vehicle Reservation*
system. The process has stages:

1. *Customer* queries the catalog and creates a reservation request (*"inquiry"*).

1. The system verifies the *inquiry* and attempts to fullfill the reservation
    or propose a close match. The system internally blocks the proposed vehicle
    from other reservation attempts while the *Customer* reviews the offer.

1. The *Customer* has 10 minutes to accept and pay the offer or reject.

1. If the *Customer* accepts the offer, the system finalizes the pre-reserved
    vehicle and sends a confirmation to the *Customer*.


&nbsp;

## Scenario of a *Vehicle Reservation*

The process starts with the *Customer* searching the catalog for vehicles,
locations and desired times.
Then, the *Customer* creates an *inquiry* with a desired vehicle, pickup
and return locations and desired times and submits the *inquiry* to the
reservation system.

The reservation system validates the *inquiry* and rejects incomplete or
unreasobable inquiries. If accepted, the system attempts to fullfill the
*inquiry*. If the *inquiry* cannot be fullfilled, the system attempts to
find a close match. The system returns an *offer* as to the customer as an
answer, including price.

While the *Customer* reviews the offer, the system temporarily blocks the
vehicle for the offered timeframe (at the same time preventing double-bookings).

The *Customer* has 10 minutes to *accept* and *pay* the offer or reject.
If the *Customer* accepts the *offer*, its status changes to *"accepted"* and
the reservation process steps forward requesting payment information from
the *Customer*.

The *Customer* provides payment information that, if accepted by the system,
initiates payment through an external provider and finalizes the reservation
as *"booked"*. The *Customer* receives a *confirmation*.

If the *Customer* does not accept the offer or does not provide valid payment
information within 10 minutes, the system cancels the temporary block of the
vehicle since no *booking* was achieved.

<!-- 
Deutsch:
Der Prozess beginnt damit, dass der *Kunde* im Katalog nach Fahrzeugen,
Standorten und den gewünschten Zeiträumen sucht. An einem bestimmten Punkt
erstellt der *Kunde* eine *Anfrage* für ein gewünschtes Fahrzeug, inklusive
Abhol- und Rückgabeort sowie der entsprechenden Zeitangaben, und übermittelt
diese an das Reservierungssystem.

Das Reservierungssystem prüft die übermittelten Daten und weist unvollständige
oder nicht umsetzbare Anfragen zurück. Ist die Anfrage zulässig, versucht das
System, sie zu erfüllen. Sollte dies nicht direkt möglich sein, sucht das
System nach einer möglichst passenden Alternative. Sobald die Anfrage erfüllt
oder eine passende Alternative gefunden wurde, wird ein *Angebot* erstellt.
Das System präsentiert dem *Kunden* dieses *Angebot* inklusive des Preises.

Während der *Kunde* das Angebot prüft, reserviert das System das Fahrzeug
vorläufig und blockiert es für diesen Zeitraum für andere Nutzer.

Der *Kunde* hat 10 Minuten Zeit, das Angebot anzunehmen und zu bezahlen oder
es abzulehnen. Akzeptiert der *Kunde* das *Angebot*, ändert sich dessen Status
auf *"angenommen"* und der Reservierungsprozess geht in die nächste Phase über,
in der die Zahlung durch den *Kunden* angefordert wird.

Der *Kunde* gibt seine Zahlungsdaten ein. Werden diese vom System akzeptiert,
wird die Zahlung über einen externen Anbieter abgewickelt und die Reservierung
als *"gebucht"* abgeschlossen. Der *Kunde* erhält daraufhin eine Bestätigung.

Nimmt der *Kunde* das Angebot nicht an oder gibt er innerhalb der 10 Minuten
keine gültigen Zahlungsdaten ein, storniert das System die vorläufige
Reservierung, indem der Reservierungsversuch gelöscht wird.
 -->


&nbsp;

## Tasks

**Task 1:** Look for repeating nouns, e.g. *inquiry*, verbs, e.g. customer
*reviews* offer and adjectives, e.g. *accepted*. Verbs indicate actions in the
UML-Activity Diagram, nouns indicate candidates of *business objects*
(see *Task 4*). Consider which actions occur simulataneously, e.g.
*"at the same time"*.

Write down lists of dominant nouns, verbs and adjectives describing progress
of the process.

**Task 2:** Draw the UML-Activity Diagram for the *Vehicle Reservation* process.

**Task 3:** Which information is relevant for the reservation system to perform
the reservation process? Name the most-relevant *Business Object (BO)* types
(entity types represented as tables in a database).

**Task 4:** Mark points in the reservation process (in the UML Activity Diagram)
where significant steps (progress or regress) occur regarding a reservation.
Name those steps, e.g. *"initiated"*, *"inquired"*, etc.

**Task 5:** Draw a UML-Statechart diagram (Zustandsdiagram) that shows the steps
of *Task 4* as states and define transitions.

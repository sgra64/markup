### Scenario of the Car Reservation System *freerider.de*

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
*freerider.de* and a rental agent (staff) will handle the case with full access
to all documents.

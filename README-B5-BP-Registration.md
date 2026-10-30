<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B5: Business Process: *New-Customer Registration (individual)*

A *Business Process (BP)* is a structured, repeatable, long-lasting (weeks,
months, years) sequence of activities performed by people, systems, or
organizations to achieve a specific business goal, e.g. to register a new
customer considering an individual (a person), not a business customer.

&nbsp;

## Scenario

The process starts with the *new customer* (still in *guest*-role) requesting
the registration form.

The *new customer* fills in the required information, including:
- name,
- address,
- contact information (phone, email),
- payment/bank information,
- agreement to the terms and conditions ([*AGB*](https://de.wikipedia.org/wiki/Allgemeine_Gesch%C3%A4ftsbedingungen)).
and completes the step with `submit`.

The system verifies the completeness of information. If information is missing,
the customer is requested to re-enter the form.

Is the registration information complete, the system initiates three sub-activities
that progress simultaneously:

1. Verification of agreement to the terms and conditions. The activity ends
    with *success*, if the agreement has been accepted, otherwise with result *failed*.

&nbsp;

2. Verification of the identity of the *new customer* (is this a real person,
    not a fake identity) using the
    [*Postident*](https://www.deutschepost.de/de/p/postident.html)
    or the online (video-based)
    [*Postident AutoID*](https://www.deutschepost.de/de/p/postident/geschaeftskunden/identifizierungsverfahren/verfahren-autoid.html)
    service with steps:

    a) The system generates a QR-code and sends the code to the *new customer*
        via the provided email-address (this also validates the email address)
        requesting to use the code in the *Postident AutoID* app or go to a
        near post office and present the QR-code.

    b) The assistant at the post office scans the QR-code, opens the associated
        identification request and asks the person to present an official
        ID card, e.g. a
        [*Personalausweis*](https://de.wikipedia.org/wiki/Personalausweis_(Deutschland))
        or a passport
        ([*Reisepass*](https://de.wikipedia.org/wiki/Reisepass)).

    c) The post assistant verifies the information from the identification
        request with the presented ID and the presenting person and
        enters the result into the identification request.

    d) The *Postident* system reports the result back to the *new customer*
        registration system where a positive answer completes the identity
        verification with *success*, a negative answer with result *failed*.

    e) The *new customer* has two weeks to complete the identification step.

&nbsp;

3. Verification of the payment/bank information provided with the registration.
    Steps:

    a) The system contacts the bank or payment service provided in the
        registration form asking to vaildate the information.

    b) A positive answer by the bank or payment service completes this sub-activity
        with *success*, a negative answer with *failed*.

    c) The bank or payment service also has two weeks to answer.

&nbsp;

4. Only if all three sub-activities ended with *success*, the registration
    process can also proceed with *success*:

    a) The system transitions the *customer (in registration)* into a regular,
        active *customer*.

    b) The system sends a confirmation about the successfull completion of
        the registration process to the *customer*.

    c) The registration process ends with *success*.

&nbsp;

5. As soon as any of the three sub-activities ends with *failure*:

    a) The other sub-activities are terminated since no positive outcome
        of the registration process is possible.

    b) The *customer* receives a notification that the registration process
        was not successfull.

    c) The registration process ends with *failure*.



&nbsp;

*Task 1:* Draw the UML-Activity Diagram for the *New-Customer Registration*
business process.


&nbsp;

*Task 2:* Answer questions: How long does the *New-Customer Registration*
process take 

1. when the *customer* has agreed to the terms and conditions, *Postident* has
    answered positively after 2 days and the bank after 10 days,
    also positively.

1. when the *customer* has **not** agreed to the terms and conditions,
    *Postident* answered positively after 2 days and the bank positively
    after 10 days.

1. when the *customer* has agreed to the terms and conditions, *Postident*
    answered **negatively** after 2 days and the bank positively
    after 10 days.

1. when the *customer* has agreed to the terms and conditions and the
    bank answered positively after 2 minutes, but the person lost interest
    and did not go the post office or use *Postident AutoID*.

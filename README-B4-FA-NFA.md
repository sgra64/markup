<!-- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -->
## B4: *Functional Requirements (FR)* and *Non-Functional Requirements (NFR)*

*Functional Requirements (FR)* are a collection of requirements that each
describe *one* specific *technical function* the system must provide.
FR define *what* a system must do in order to be functional.

*Non-Functional Requirement (NFR)* are a collection of requirements that each
describe *one* specific *non-technical* requirement.
NFRs define *how well* the system must perform its functions.

Both use the same format:

`<ID>: The system <MUST|SHOULD> <PERFORM-FUNCTION>`.

Example FR: `FR#0010: The system must print the list of products.`

Example NFR: `NFR#0010: The system must store at least 10,000 products.`

`MUST` criteria express mandatory (in contracts: legally binding) requirements.
`SHOULD` criteria express desirable properties or behavior and are not legally
binding, hence are unnecessary in legal contracts.

While functional requirements describe specific functions, non-functional
requirements can be grouped into

- *Quantitative NFR* refer to quantities, e.g.

    - How many users need to be supported, e.g. 1000, 10k, 100k,
        1M, 10M, 100M, 1B users?

    - How many reservations must be processed in peak times?

    - How much storage is needed for the database, e.g. 1TB, 100TB, 100PB?

    - How many machines are needed in the *Cloud* (1, 2, 10, 100, ...)?

    - How long does data need to be stored (1 week, 1 month, 1 year, 10 years, ...)?

- *Qualitative NFR* refer to other properties releated to:

    1. Performance & Scalability

        - Latency / Response Time: How quickly the system responds to an action.
            > *Example:* "The app must process payment transactions in under 2 seconds."

        - Throughput: How many requests the system can handle simultaneously.
            > *Example:* "The system must support up to 10,000 active concurrent users during peak hours."

    1. Security & Compliance

        - Data Protection & Privacy: How customer and system data is protected.
            > *Example:* "All sensitive payment data must be PCI-DSS compliant and encrypted at rest using AES-256."

        - Authentication & Authorization: Who can access what data.
            > *Example:* "User passwords must meet NIST complexity standards and support multi-factor authentication (MFA)."

    1. Reliability & Availability

        - Uptime / Availability: How consistently the system remains operational.
            > *Example:* "The reservation backend must achieve 99.9% uptime (less than 8.7 hours of downtime per year)."

        - Fault Tolerance & Recovery: How the system recovers from unexpected failures.
            > *Example:* "In the event of a database crash, the system must recover state within 5 minutes without data loss."

    1. Usability & Accessibility

        - Accessibility: Ease of use for users with disabilities (e.g., WCAG guidelines).

        - Ease of Use: How quickly a new user can learn to navigate the interface.
            > *Example:* "A first-time user should be able to complete a car reservation in fewer than 4 taps."

    1. Maintainability & Portability

        - Compatibility: Operating systems, browsers, or devices supported.
            > *Example:* "The app must support iOS 16+ and Android 12+ on screen sizes from 4.7 inches upward."

        - Maintainability: How easily developers can modify or update code without introducing bugs.


<!-- 
    - Appearance - styling of the user interface.

    - Usability - defines 

    - Learnability, Understandability - 

    - Availability - 

    - Reliability, Stability - 

    - Accuracy - 

    - Adaptability - 

    - Security -

    - Data protection - 
 -->

*Non-Functional Requirement (NFR)* must be precise with concrete measurable
acceptance criteria.

- > *Bad Example:* `NFA0010: The system must be easy to use.`

    - useless statement because no concrete acceptance criteria is given.

- > *Good Example:* `NFA0010: The system must perform the main use case in at-most three clicks.`

    - a concrete acceptance criteria is given.




&nbsp;

*Task 1:* Write 10 *Functional Requirements (FR)* for the car-reservation
use cases.


&nbsp;

*Task 2:* Write 5 reasonable *Non-Functional Requirement (NFR)* for the
car-reservation system. Assume operation in three main cities: Berlin,
Frankfurt(M) and Munich.

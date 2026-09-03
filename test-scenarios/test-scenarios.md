# EventHub — Test Scenarios

## 1. Overview

This document contains the test scenarios designed for the EventHub application based on the functional requirements defined in the project.

The scenarios cover functional, positive, negative, boundary, and authorization testing.

---

## 2. Test Scenarios

| ID   | Requirement | Test Scenario                                                                                     | Type                |
| ---- | ----------- | ------------------------------------------------------------------------------------------------- | ------------------- |
| TS01 | REQ-01      | Verify that the user can search for an event by name.                                             | Functional          |
| TS02 | REQ-01      | Verify that the search returns relevant events based on the search term.                          | Functional          |
| TS03 | REQ-02      | Verify that the user can filter events by category.                                               | Functional          |
| TS04 | REQ-02      | Verify that the user can filter events by date.                                                   | Functional          |
| TS05 | REQ-02      | Verify that the user can filter events by location.                                               | Functional          |
| TS06 | REQ-03      | Verify that the user can reserve between 1 and 6 tickets per reservation.                         | Boundary            |
| TS07 | REQ-03      | Verify that the user cannot reserve more than 6 tickets per reservation.                          | Negative / Boundary |
| TS08 | REQ-04      | Verify that the user can reserve available tickets for an event.                                  | Positive            |
| TS09 | REQ-04      | Verify that the user cannot reserve unavailable tickets.                                          | Negative            |
| TS10 | REQ-05      | Verify that the user can cancel an existing reservation.                                          | Functional          |
| TS11 | REQ-05      | Verify that the number of available tickets increases after a reservation is cancelled.           | Functional          |
| TS12 | REQ-05      | Verify that the user can make a new reservation after cancelling a previous reservation.          | Functional          |
| TS13 | REQ-06      | Verify that the user cannot confirm a reservation without providing valid payment information.    | Negative            |
| TS14 | REQ-06      | Verify that the system does not confirm a reservation when the payment fails.                     | Negative            |
| TS15 | REQ-07      | Verify that the system displays a reservation confirmation after a successful payment.            | Positive            |
| TS16 | REQ-07      | Verify that the system does not display a reservation confirmation after an unsuccessful payment. | Negative            |
| TS19 | REQ-01      | Verify that the user can select an event from the search results.                                 | Functional          |
| TS20 | REQ-04      | Verify that the user can proceed to payment after selecting tickets for a reservation.            | Functional          |
| TS21 | REQ-05      | Verify that the user can only cancel their own reservations.                                      | Authorization       |

---

## 3. Test Coverage

The scenarios provide coverage for the main EventHub functionalities:

### Event Search

* Search events by name.
* Validate search relevance.
* Select an event from search results.

### Event Filtering

* Filter by category.
* Filter by date.
* Filter by location.

### Ticket Reservation

* Validate minimum and maximum ticket quantities.
* Prevent reservations exceeding the maximum quantity.
* Reserve available tickets.
* Prevent reservations for unavailable tickets.
* Proceed to payment after selecting tickets.

### Reservation Cancellation

* Cancel an existing reservation.
* Validate ticket availability after cancellation.
* Create a new reservation after cancellation.
* Prevent users from cancelling reservations belonging to other users.

### Payment

* Validate payment information.
* Prevent confirmation after unsuccessful payment.

### Reservation Confirmation

* Display confirmation after successful payment.
* Prevent confirmation after unsuccessful payment.

---

## 4. Testing Techniques

The scenarios apply different testing techniques and approaches:

* **Functional Testing** — validates whether the application performs its intended functions.
* **Positive Testing** — verifies expected behavior using valid inputs and conditions.
* **Negative Testing** — verifies how the system behaves with invalid inputs or conditions.
* **Boundary Testing** — focuses on limits such as the maximum of 6 tickets per reservation.
* **Authorization Testing** — verifies that users can only perform actions they are authorized to perform.

---

## 5. Traceability

Each test scenario is linked to at least one functional requirement.

This creates a basic traceability relationship between requirements and testing activities:

**Requirement → Test Scenario → Test Case → Test Execution**

This approach helps ensure that the defined requirements are covered by the QA process.


Note: TS17 and TS18 were intentionally excluded because their expected behavior was not explicitly defined in the available requirements.

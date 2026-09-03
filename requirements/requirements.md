# EventHub — Requirements

## 1. Overview

This document defines the functional requirements used as the basis for testing the EventHub application.

The requirements describe the main functionalities of the platform, including event search, filtering, ticket reservation, cancellation, payment validation, and reservation confirmation.

These requirements are used to derive test scenarios and test cases throughout the QA project.

---

## 2. Functional Requirements

### REQ-01 — Event Search

The system shall allow users to search for events by name.

**Expected behavior:**

* The user can enter an event name in the search field.
* The system returns events matching the search criteria.

---

### REQ-02 — Event Filters

The system shall allow users to filter events by:

* Category
* Date
* Location

**Expected behavior:**

* Users can apply one or more available filters.
* The displayed events should match the selected filtering criteria.

---

### REQ-03 — Ticket Quantity

The system shall allow users to select between **1 and 6 tickets** per reservation.

**Expected behavior:**

* A user can reserve a minimum of 1 ticket.
* A user can reserve a maximum of 6 tickets.
* The system must prevent reservations containing more than 6 tickets.

---

### REQ-04 — Ticket Reservation

The system shall allow users to reserve tickets for events with available tickets.

**Expected behavior:**

* Users can select an available event.
* Users can select the desired number of tickets.
* The system allows the reservation to proceed when tickets are available.

---

### REQ-05 — Reservation Cancellation

The system shall allow users to cancel their existing reservations.

**Expected behavior:**

* Users can access their existing reservations.
* Users can cancel their own reservations.
* Tickets associated with a cancelled reservation become available again.

---

### REQ-06 — Payment Validation

The system shall require valid payment information before confirming a reservation.

**Expected behavior:**

* Valid payment information allows the reservation to proceed.
* Invalid payment information must be rejected.
* A reservation must not be confirmed when payment is unsuccessful.

---

### REQ-07 — Reservation Confirmation

The system shall display a reservation confirmation after a successful payment.

**Expected behavior:**

* A successful payment results in a confirmed reservation.
* The system displays a reservation confirmation.
* An unsuccessful payment must not result in a reservation confirmation.

---

## 3. Requirements Summary

| ID     | Requirement              | Priority |
| ------ | ------------------------ | -------- |
| REQ-01 | Event Search             | High     |
| REQ-02 | Event Filters            | Medium   |
| REQ-03 | Ticket Quantity          | High     |
| REQ-04 | Ticket Reservation       | High     |
| REQ-05 | Reservation Cancellation | High     |
| REQ-06 | Payment Validation       | Critical |
| REQ-07 | Reservation Confirmation | High     |

---

## 4. Traceability

The requirements defined in this document are used as the basis for the project's test scenarios and test cases.

The testing flow is:

**Requirements → Test Scenarios → Test Cases → Test Execution → Bug Reports → Retesting**

This traceability helps ensure that the main application requirements are covered by the QA activities performed in the project.


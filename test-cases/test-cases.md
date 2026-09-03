# EventHub — Test Cases

## 1. Overview

This document contains the detailed test cases selected for the initial execution cycle of the EventHub QA project.

The test cases were derived from the previously defined test scenarios and cover functional, boundary, and negative testing.

---

## 2. Test Cases

### TC01 — Search for an event by name

**Requirement:** REQ-01
**Test Scenario:** TS01
**Test Type:** Functional / Positive

#### Preconditions

* The EventHub website is accessible.
* At least one event exists in the system.

#### Test Data

* Event: Rock Festival
* Search term: Rock Festival

#### Test Steps

1. Open the EventHub website.
2. Enter the event name "Rock Festival" in the search bar.
3. Submit the search.

#### Expected Result

The searched event is displayed in the search results.

#### Execution Result

**PASS**

---

### TC02 — Verify that the user cannot reserve more than 6 tickets

**Requirement:** REQ-03
**Test Scenario:** TS07
**Test Type:** Negative / Boundary

#### Preconditions

* The EventHub website is accessible.
* At least one event with available tickets exists.

#### Test Data

* Event: Rock Festival
* Available tickets: 10
* Maximum tickets per reservation: 6
* Tickets to reserve: 7

#### Test Steps

1. Access the EventHub website.
2. Select the "Rock Festival" event.
3. Select 7 tickets for the reservation.
4. Attempt to proceed with the reservation.

#### Expected Result

The system prevents the user from reserving more than 6 tickets in a single reservation.

#### Actual Result

The system allows the user to select 7 tickets in a single reservation.

#### Execution Result

**FAIL**

**Related Bug:** BUG-001

---

### TC03 — Verify that available tickets increase after a reservation is cancelled

**Requirement:** REQ-05
**Test Scenario:** TS11
**Test Type:** Functional / Positive

#### Preconditions

* The EventHub website is accessible.
* The user is logged in.
* The Rock Festival event has at least 10 available tickets.
* The user has an existing reservation for the Rock Festival.

#### Test Data

* Event: Rock Festival
* Initial available tickets: 10
* Tickets in existing reservation: 2

#### Test Steps

1. Access the EventHub website.
2. Navigate to "My Reservations".
3. Open the existing Rock Festival reservation.
4. Cancel the reservation.
5. Return to the Rock Festival event page.
6. Check the number of available tickets.

#### Expected Result

The number of available tickets increases by the number of tickets from the cancelled reservation, returning to 10 available tickets.

#### Execution Result

**PASS**

---

### TC04 — Unsuccessful payment does not confirm reservation

**Requirement:** REQ-06 / REQ-07
**Test Scenario:** TS16
**Test Type:** Negative

#### Preconditions

* The EventHub website is accessible.
* The user is logged in.
* The user has selected an available event.
* The user has selected the tickets and proceeded to the payment page.

#### Test Data

* Event: Rock Festival
* Payment information: Invalid

#### Test Steps

1. Enter invalid payment information.
2. Attempt to confirm the reservation.

#### Expected Result

The system does not confirm the reservation and does not display a reservation confirmation.

#### Actual Result

The system confirms the reservation and displays a reservation confirmation even when invalid payment information is provided.

#### Execution Result

**FAIL**

**Related Bug:** BUG-002

---

## 3. Test Execution Summary

| Test Case | Requirement     | Type                  | Result | Related Bug |
| --------- | --------------- | --------------------- | ------ | ----------- |
| TC01      | REQ-01          | Functional / Positive | ✅ PASS | —           |
| TC02      | REQ-03          | Negative / Boundary   | ❌ FAIL | BUG-001     |
| TC03      | REQ-05          | Functional / Positive | ✅ PASS | —           |
| TC04      | REQ-06 / REQ-07 | Negative              | ❌ FAIL | BUG-002     |

### Summary

* **Total Test Cases:** 4
* **Passed:** 2
* **Failed:** 2
* **Initial Pass Rate:** 50%
* **Bugs Identified:** 2

Both identified defects were reported in Jira, followed through the defect lifecycle, and successfully retested after being fixed.

---

## 4. Traceability

The test cases maintain traceability between requirements, test scenarios, execution results, and defects.

| Requirement     | Test Scenario | Test Case | Result | Bug     |
| --------------- | ------------- | --------- | ------ | ------- |
| REQ-01          | TS01          | TC01      | PASS   | —       |
| REQ-03          | TS07          | TC02      | FAIL   | BUG-001 |
| REQ-05          | TS11          | TC03      | PASS   | —       |
| REQ-06 / REQ-07 | TS16          | TC04      | FAIL   | BUG-002 |

The testing flow is:

**Requirement → Test Scenario → Test Case → Test Execution → Bug Report → Retest**

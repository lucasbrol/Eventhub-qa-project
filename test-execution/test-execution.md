# EventHub — Test Execution Report

## 1. Overview

This document summarizes the initial test execution cycle performed for the EventHub QA project.

The objective of the execution was to validate selected application functionalities and identify defects based on the previously defined test cases.

A total of **4 test cases** were executed.

---

## 2. Execution Scope

The execution covered the following functionalities:

* Event search
* Ticket quantity validation
* Reservation cancellation
* Payment validation
* Reservation confirmation

The selected test cases were designed to cover functional, positive, negative, and boundary testing.

---

## 3. Test Environment

| Field        | Value          |
| ------------ | -------------- |
| Environment  | Test           |
| Platform     | Web            |
| Application  | EventHub       |
| Testing Type | Manual Testing |

---

## 4. Test Execution Results

| Test Case | Description                                       | Result |
| --------- | ------------------------------------------------- | ------ |
| TC01      | Search for an event by name                       | ✅ PASS |
| TC02      | Cannot reserve more than 6 tickets                | ❌ FAIL |
| TC03      | Available tickets increase after cancellation     | ✅ PASS |
| TC04      | Unsuccessful payment does not confirm reservation | ❌ FAIL |

---

## 5. Detailed Results

### TC01 — Search for an event by name

**Result:** PASS

The user was able to search for an event by name, and the searched event was displayed in the search results.

---

### TC02 — Maximum ticket quantity per reservation

**Result:** FAIL

**Expected Result:**
The system should prevent the user from reserving more than 6 tickets in a single reservation.

**Actual Result:**
The system allowed the user to select 7 tickets in a single reservation.

**Action:**
A bug report was created in Jira.

**Related Bug:** BUG-001

---

### TC03 — Available tickets after reservation cancellation

**Result:** PASS

The number of available tickets increased correctly after the reservation was cancelled.

---

### TC04 — Unsuccessful payment does not confirm reservation

**Result:** FAIL

**Expected Result:**
The system should not confirm the reservation or display a reservation confirmation after an unsuccessful payment.

**Actual Result:**
The system confirmed the reservation and displayed a reservation confirmation even when invalid payment information was provided.

**Action:**
A bug report was created in Jira.

**Related Bug:** BUG-002

---

## 6. Execution Summary

| Metric            | Result |
| ----------------- | -----: |
| Total Test Cases  |      4 |
| Passed            |      2 |
| Failed            |      2 |
| Initial Pass Rate |    50% |
| Bugs Identified   |      2 |

### Initial Execution Status

**50% of the executed test cases passed during the initial execution cycle.**

The two failed test cases resulted in two high-priority bug reports.

---

## 7. Defect Follow-up

The identified defects were managed through the Jira defect lifecycle.

### BUG-001

**Issue:** The system allowed users to reserve more than 6 tickets.

**Initial Test Result:** FAIL

**Retest Result:** PASS

The defect was fixed and successfully validated during retesting.

---

### BUG-002

**Issue:** The system confirmed reservations when invalid payment information was provided.

**Initial Test Result:** FAIL

**First Retest:** FAIL

The issue remained reproducible after the initial fix attempt and was reopened.

**Second Retest:** PASS

The defect was fixed and successfully validated during the second retest.

---

## 8. Final Status

After the identified defects were fixed and successfully retested:

* All executed test cases were ultimately validated successfully.
* BUG-001 was successfully fixed and closed.
* BUG-002 required an additional fix cycle before passing retest.
* Both defects were successfully closed in Jira.

The initial execution identified issues that were not detected through test case design alone, demonstrating the importance of executing tests and validating actual system behavior.

---

## 9. QA Workflow

The execution followed the following QA process:

**Requirements → Test Scenarios → Test Cases → Test Execution → Bug Reporting → Fix → Retest → Closure**

This workflow was managed using Jira for defect tracking and lifecycle management.

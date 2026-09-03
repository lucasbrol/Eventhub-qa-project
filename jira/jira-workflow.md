# EventHub — Jira Workflow

## 1. Overview

Jira was used throughout the EventHub QA project to manage defects and simulate a real-world software development and QA workflow.

The workflow was designed to represent the interaction between development and QA teams, from the initial creation of a bug through investigation, fixing, testing, retesting, and final closure.

---

## 2. Workflow

The main defect workflow is:

```text
To Do
  ↓
In Progress
  ↓
In Review
  ↓
Ready for QA
  ↓
Testing
  ↓
Done
```

When a defect fails during testing, it can be reopened:

```text
Testing
  ↓
Reopened
  ↓
In Progress
  ↓
In Review
  ↓
Ready for QA
  ↓
Testing
  ↓
Done
```

---

## 3. Status Definitions

| Status       | Description                                                   |
| ------------ | ------------------------------------------------------------- |
| To Do        | The issue has been created but work has not started.          |
| In Progress  | The issue is currently being investigated or fixed.           |
| In Review    | The fix or work is ready for review before being sent to QA.  |
| Ready for QA | The issue has been reviewed and is ready for QA validation.   |
| Testing      | QA is validating the fix or testing the issue.                |
| Reopened     | The issue failed during testing and requires additional work. |
| Done         | The issue has been successfully validated and closed.         |

---

## 4. Transitions

| From         | To           | Transition        |
| ------------ | ------------ | ----------------- |
| To Do        | In Progress  | Start Progress    |
| In Progress  | In Review    | Submit for Review |
| In Review    | Ready for QA | Send to QA        |
| Ready for QA | Testing      | Start Testing     |
| Testing      | Done         | Pass Testing      |
| Testing      | Reopened     | Reopen Bug        |
| Reopened     | In Progress  | Start Fix         |

---

## 5. Defect Lifecycle Example

### BUG-001

BUG-001 followed the standard workflow:

**To Do → In Progress → In Review → Ready for QA → Testing → Done**

The fix was successfully validated during retesting.

---

### BUG-002

BUG-002 demonstrated a more complex defect lifecycle:

**To Do → In Progress → In Review → Ready for QA → Testing**

The first retest failed, so the issue was reopened:

**Testing → Reopened → In Progress**

After another fix cycle, the issue returned to QA:

**In Progress → In Review → Ready for QA → Testing → Done**

The second retest passed successfully.

---

## 6. QA Responsibilities Simulated

Through this workflow, the project simulated several QA responsibilities:

* Reviewing reported issues.
* Validating fixes.
* Executing test cases.
* Documenting test results.
* Reporting defects.
* Retesting resolved defects.
* Reopening defects when the issue remains reproducible.
* Closing defects after successful validation.

---

## 7. Project Workflow

The complete QA workflow used in the EventHub project can be summarized as:

```text
Requirements
     ↓
Test Scenarios
     ↓
Test Cases
     ↓
Test Execution
     ↓
Bug Report
     ↓
Development Fix
     ↓
QA Retest
     ↓
     ├── PASS → Done
     │
     └── FAIL → Reopened → Fix → Retest
```

This workflow demonstrates the relationship between test planning, execution, defect management, and validation within the QA process.

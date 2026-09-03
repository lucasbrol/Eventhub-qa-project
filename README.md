# EventHub — QA Testing Project

A practical QA testing project focused on manual software testing, test scenario design, test case creation, test execution, bug reporting, retesting, and Jira workflow management.

## 📌 Project Overview

**EventHub** is a simulated event discovery and ticket booking platform created for QA practice.

The project was designed to simulate a real-world QA workflow, from analyzing requirements and designing test scenarios to executing tests, reporting defects, retesting fixes, and closing issues.

The main goal of this project is to demonstrate practical knowledge of **Quality Assurance and Software Testing**, including functional testing, negative testing, boundary testing, authorization testing, defect management, and QA documentation.

> **Project Type:** QA Simulation / Testing Project
> **Testing Approach:** Manual Testing
> **Project Management:** Jira
> **Documentation:** Markdown
> **Language:** English

---

## 🎯 Objectives

The main objectives of this project are:

* Practice software testing in a simulated real-world environment.
* Create test scenarios based on system requirements.
* Design detailed test cases.
* Execute test cases and document results.
* Identify and report software defects.
* Apply severity and priority concepts.
* Practice bug lifecycle management.
* Perform retesting after defect fixes.
* Use Jira to manage QA activities.
* Maintain professional QA documentation in English.

---

## 🧩 Application Scope

The EventHub platform includes the following main functionalities:

* Event search by name
* Event filtering by category, date, and location
* Event selection
* Ticket quantity selection
* Ticket reservation
* Reservation cancellation
* Payment validation
* Reservation confirmation

### Business Requirements

| ID     | Requirement                                                       |
| ------ | ----------------------------------------------------------------- |
| REQ-01 | Users can search for events by name.                              |
| REQ-02 | Users can filter events by category, date, and location.          |
| REQ-03 | Users can reserve between 1 and 6 tickets per reservation.        |
| REQ-04 | Users can reserve available tickets.                              |
| REQ-05 | Users can cancel existing reservations.                           |
| REQ-06 | Valid payment information is required to confirm a reservation.   |
| REQ-07 | A reservation confirmation is displayed after successful payment. |

---

## 🧪 Testing Activities

The project covers the following QA activities:

* Requirement analysis
* Test scenario design
* Test case design
* Functional testing
* Positive testing
* Negative testing
* Boundary testing
* Authorization testing
* Test execution
* Defect reporting
* Bug lifecycle management
* Retesting
* Test result documentation

---

## 📋 Test Scenarios

A total of **19 test scenarios** were designed based on the application requirements.

The scenarios cover:

* Event search
* Event filtering
* Ticket reservation
* Ticket quantity boundaries
* Reservation availability
* Reservation cancellation
* Payment validation
* Reservation confirmation
* Authorization

The complete scenarios can be found in:

📁 [`Test Scenarios`](test-scenarios/test-scenarios.md)

---

## 🧪 Test Cases

Four test cases were selected for the initial execution cycle.

| ID   | Test Case                                         | Result |
| ---- | ------------------------------------------------- | ------ |
| TC01 | Search for an event by name                       | ✅ PASS |
| TC02 | Cannot reserve more than 6 tickets                | ❌ FAIL |
| TC03 | Available tickets increase after cancellation     | ✅ PASS |
| TC04 | Unsuccessful payment does not confirm reservation | ❌ FAIL |

Detailed test cases can be found in:

📁 [`Test Cases`](test-cases/test-cases.md)

---

## 📊 Test Execution

### Initial Execution

**Total Test Cases:** 4
**Passed:** 2
**Failed:** 2
**Initial Pass Rate:** 50%

The two failed test cases resulted in defect reports.

### Defects Identified

| Bug     | Description                                                  | Priority | Final Result |
| ------- | ------------------------------------------------------------ | -------- | ------------ |
| BUG-001 | System allows users to reserve more than 6 tickets           | High     | ✅ Fixed      |
| BUG-002 | System confirms reservation with invalid payment information | High     | ✅ Fixed      |

Both defects were followed through the Jira workflow and successfully retested after being fixed.

Detailed execution results:

📁 [`Test Execution Report`](test-execution/execution-report.md)

---

## 🐛 Bug Reports

### BUG-001 — Maximum Ticket Quantity

**Issue:** The system allowed users to select more than the maximum allowed quantity of 6 tickets.

**Initial Result:** Failed
**Priority:** High
**Final Result:** Fixed and successfully retested

📁 [`BUG-001`](bug-reports/BUG-001.md)

### BUG-002 — Invalid Payment

**Issue:** The system confirmed a reservation when invalid payment information was provided.

**Initial Result:** Failed
**Priority:** High
**First Retest:** Failed
**Second Retest:** Passed
**Final Result:** Fixed and successfully retested

📁 [`BUG-002`](bug-reports/BUG-002.md)

---

## 🔄 Jira Workflow

The project used Jira to simulate a professional defect management workflow.

### Workflow

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

When a defect fails during retesting:

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

This workflow was used to simulate the interaction between development and QA teams, including defect fixing, QA validation, retesting, reopening defects, and final closure.

📁 [`Jira Workflow`](jira/jira-workflow.md)

---

## 🛠️ Tools & Technologies

* **Jira** — Issue tracking and QA workflow management
* **Markdown** — QA documentation
* **GitHub** — Version control and project documentation

### QA Concepts Practiced

* Functional Testing
* Negative Testing
* Boundary Value Analysis
* Authorization Testing
* Test Case Design
* Defect Lifecycle
* Retesting
* Test Execution
* Severity & Priority
* Requirements-based Testing

---

## 📁 Project Structure

```text
eventhub-qa-project/
│
├── README.md
│
├── test-scenarios/
│   └── test-scenarios.md
│
├── test-cases/
│   └── test-cases.md
│
├── test-execution/
│   └── execution-report.md
│
├── bug-reports/
│   ├── BUG-001.md
│   └── BUG-002.md
│
└── jira/
    └── jira-workflow.md
```

---

## 📈 Future Improvements

This project will be expanded as new QA skills are developed.

Planned improvements include:

* API testing with Postman
* SQL database validation
* Git and GitHub workflows
* Automated testing
* Playwright
* API automation
* Test reporting
* CI/CD integration with GitHub Actions

The objective is to progressively transform this project from a manual testing exercise into a more complete QA portfolio project.

---

## 👨‍💻 About This Project

This project was created as part of my practical study in **Quality Assurance and Software Testing**, with a focus on developing hands-on experience and building a professional QA portfolio.

The project emphasizes not only test execution, but also the complete QA process: **planning, documentation, execution, defect management, retesting, and reporting**.

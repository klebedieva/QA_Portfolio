# Bistro Web Application — Manual QA Project

## Project Overview

This repository contains manual QA documentation for the **Bistro web application**, originally developed as part of my **Bac+2 Web Developer diploma project**. I later used the application as the basis for an independent QA project to demonstrate my skills in requirements analysis, test planning, test design, test execution, defect reporting, and requirements traceability.

The current testing scope focuses on the **Menu** page and covers category, search, price, dietary, and combined filter functionality.

**Application under test:** [Bistro Web Application](https://bistro-template.onrender.com)

## Project Objectives

- Analyze the Menu page filtering functionality.
- Prepare a structured test strategy and Test Plan.
- Design and execute functional end-to-end test cases.
- Validate individual filters and combinations of multiple filters.
- Identify, document, and prioritize functional defects.
- Demonstrate requirement-to-test-case traceability.
- Summarize the execution results, risks, and recommendations.

## Scope

### In scope

- Category filters
- Search functionality
- Price filters
- Dietary filters
- Combined filters
- Default filter states
- Filter selection, switching, clearing, and reset behavior
- Empty-state behavior
- Price boundary values
- AND logic for multiple active filters

### Out of scope

- Cart functionality
- Checkout process
- Reservation functionality
- Contact form
- API testing
- Performance testing
- Security testing
- Cross-browser and mobile compatibility testing
- Test automation

## QA Documentation

| Deliverable | Description |
|---|---|
| [Test Plan](Test%20Plan/Test%20Plan.md) | Defines the project scope, objectives, test strategy, environment, deliverables, entry and exit criteria, risks, and schedule. |
| [Category Filters Test Cases](Test%20Cases/Menu/Search%20%26%20Filters/Category-Filters-Test-Cases.md) | 9 test cases covering category-filter behavior. |
| [Search Filters Test Cases](Test%20Cases/Menu/Search%20%26%20Filters/Search-Filters-Test-Cases.md) | 10 test cases covering Menu search functionality. |
| [Price Filters Test Cases](Test%20Cases/Menu/Search%20%26%20Filters/Price-Filters-Test-Cases.md) | 8 test cases covering price ranges and boundary values. |
| [Dietary Filters Test Cases](Test%20Cases/Menu/Search%20%26%20Filters/Dietary-Filters-Test-Cases.md) | 8 test cases covering individual and multiple dietary filters. |
| [Combined Filters Test Cases](Test%20Cases/Menu/Search%20%26%20Filters/Combined-Filters-Test-Cases.md) | 8 test cases covering pairwise and simultaneous filter combinations. |
| [Requirements Evidence](Requirements/screenshots/) | Category-filtering requirement and traceability demonstrated in Squash TM. |
| [Bug Reports](Bug%20Reports/) | 4 defects documented separately with severity, priority, reproduction steps, actual and expected results, and supporting evidence. |
| [Test Summary Report](Test%20Summary/Test-Summary-Report.md) | Presents execution results, failed scenarios, defect distribution, risks, recommendations, and the final testing conclusion. |

## Test Case Coverage

| Test suite | Number of test cases | Main coverage |
|---|---:|---|
| Category Filters | 9 | Default category, individual categories, switching, active state, and reset behavior |
| Search Filters | 10 | Default state, exact and partial search, whitespace, case sensitivity, special characters, and multiple results |
| Price Filters | 8 | Available ranges, filtering, reset behavior, dynamic updates, and boundary values |
| Dietary Filters | 8 | Individual preferences, multiple selections, AND logic, and clearing filters |
| Combined Filters | 8 | Pairwise filter combinations, empty state, and simultaneous use of all filter types |
| **Total** | **43** | |

## Test Execution Results

| Metric | Result |
|---|---:|
| Total test cases | 43 |
| Executed | 43 |
| Passed | 39 |
| Failed | 4 |
| Blocked | 0 |
| Not executed | 0 |
| Pass rate | 90.7% |

## Identified Defects

| ID | Defect | Severity | Priority | Status |
|---|---|---|---|---|
| BUG-001 | Search returns unrelated menu items for a partial keyword | Normal | Medium | Open |
| BUG-002 | Search does not handle leading and trailing whitespace correctly | Minor | Low | Open |
| BUG-003 | Empty-state message is not displayed when filters return no matching items | Normal | Medium | Open |
| BUG-004 | Multiple dietary filters use OR logic instead of AND logic | Major | High | Open |

## Key Findings

- Category filtering works correctly for all available categories.
- Price filtering works correctly, including the boundary values of 15 € and 25 €.
- Search input is not normalized before filtering, causing queries with surrounding spaces to fail.
- Partial keyword matching can return an unrelated menu item.
- No informative empty-state message is displayed when active filters return no results.
- Multiple dietary filters use OR logic instead of the expected AND logic.

## Tools Used

| Tool | Usage |
|---|---|
| Qase | Creation and management of 43 test cases and 4 defect reports |
| Squash TM | Category-filtering requirement, related test cases, and requirement-to-test-case traceability |
| GitHub | Organization and presentation of the Test Plan, test cases, requirements evidence, bug reports, screenshots, and Test Summary Report |

## Test Design Techniques

- Equivalence partitioning
- Boundary value analysis
- Decision table testing
- State transition testing
- Pairwise testing
- Positive and negative testing
- Exploratory testing

## Repository Structure

```text
Manual Testing/
└── Restaurant Web Application/
    ├── Bug Reports/
    │   ├── screenshots/
    │   │   ├── qase-defect-report-example.png
    │   │   └── qase-defects-overview.png
    │   ├── BUG-001-partial-search-results.md
    │   ├── BUG-002-search-whitespace.md
    │   ├── BUG-003-empty-state-message.md
    │   └── BUG-004-dietary-filters-or-logic.md
    ├── Requirements/
    │   └── screenshots/
    ├── Test Cases/
    │   ├── Menu/
    │   │   └── Search & Filters/
    │   │       ├── Category-Filters-Test-Cases.md
    │   │       ├── Combined-Filters-Test-Cases.md
    │   │       ├── Dietary-Filters-Test-Cases.md
    │   │       ├── Price-Filters-Test-Cases.md
    │   │       └── Search-Filters-Test-Cases.md
    │   └── screenshots/
    │       ├── qase-category-filters-test-cases.png
    │       ├── qase-test-case-properties-example.png
    │       ├── qase-test-case-steps-example.png
    │       └── squash-test-case-example.png
    ├── Test Plan/
    │   └── Test Plan.md
    ├── Test Summary/
    │   └── Test-Summary-Report.md
    └── README.md
```

## Conclusion

All 43 planned test cases were executed: **39 passed and 4 failed**, resulting in a **90.7% pass rate**.

The core category and price-filtering functionality works as expected. However, four defects remain open, including one major defect affecting the logic of multiple dietary filters. The tested functionality is therefore considered **partially successful but not ready for final acceptance** until the identified defects are fixed and the failed scenarios are successfully retested.

## Author

**Karyna Lebedieva**  
Manual QA / Functional Tester

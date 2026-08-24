# Search Filters — Test Cases

## Overview

This document contains functional end-to-end test cases for the search functionality on the **Menu** page of the Bistro web application.

**Feature:** Menu item search  
**Test type:** Functional  
**Test level:** End-to-end (E2E)  
**Test design techniques:** Equivalence partitioning, boundary-oriented input validation, and negative testing  
**Tools:** Qase, Squash TM  
**Automation status:** Not automated

## Test coverage

- Default search-field state
- Exact and partial queries
- Queries with no matches
- Clearing and changing a query
- Leading and trailing spaces
- Special characters
- Case insensitivity
- Multiple matching results

---

## TC-SF-001 — Verify the default state of the search field on page load

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the search field is displayed correctly and is ready for user interaction when the Menu page is opened.

**Preconditions:** None.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the Menu page. | The Menu page loads successfully. |
| 2 | Observe the search field. | The search field is visible, enabled, and empty by default. |
| 3 | Observe the placeholder text. | The correct placeholder text is displayed inside the search field. |

**Postcondition:** The user remains on the Menu page.

---

## TC-SF-002 — Verify filtering by an exact search query

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the search functionality displays only menu items matching an exact query.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item matching the exact query exists.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a complete menu item name in the search field. | The entered text is displayed correctly in the search field. |
| 2 | Observe the displayed menu items. | Only menu items matching the exact query are displayed. Non-matching items are hidden. |

**Postcondition:** The entered search query remains applied.

---

## TC-SF-003 — Verify filtering by a partial search query

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the search functionality displays menu items containing the entered partial keyword.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item partially matching the query exists.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter part of a menu item name in the search field. | The entered text is displayed correctly in the search field. |
| 2 | Observe the displayed menu items. | Only menu items containing the partial keyword are displayed. Non-matching items are hidden. |

**Postcondition:** The entered search query remains applied.

---

## TC-SF-004 — Verify a search query with no matching items

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Negative |
| Status | Actual |

**Description:** Verify application behavior when the entered query does not match any available menu item.

**Preconditions:**

- The user is on the Menu page.
- No menu item matches the test query.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a query that does not match any existing menu item. | The entered text is displayed correctly in the search field. |
| 2 | Observe the displayed menu items. | No menu items are displayed for the entered query. The page remains stable and usable. |

**Postcondition:** The entered search query remains applied.

---

## TC-SF-005 — Verify that clearing the search field resets the results

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that clearing the search field restores the default menu display.

**Preconditions:**

- The user is on the Menu page.
- At least one searchable menu item is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a menu item name in the search field. | Only items matching the query are displayed. Non-matching items are hidden. |
| 2 | Clear the search field. | The search field becomes empty. |
| 3 | Observe the displayed menu items. | All available menu items from all categories are displayed. |

**Postcondition:** The search field is empty, and all available menu items are displayed.

---

## TC-SF-006 — Verify that leading and trailing spaces are ignored

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that leading and trailing spaces do not affect the search results.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item matching the trimmed query exists.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a valid menu item name with leading and trailing spaces. | The entered text is displayed in the search field. |
| 2 | Observe the displayed menu items. | The spaces are ignored for filtering. Only items matching the trimmed query are displayed, and non-matching items are hidden. |

**Postcondition:** The entered search query remains applied.

> **Defect coverage:** If valid matching items are not returned because of surrounding spaces, record the result as failed and link the corresponding bug report.

---

## TC-SF-007 — Verify that results update when the query is changed

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that displayed results update dynamically when the search query is modified.

**Preconditions:**

- The user is on the Menu page.
- Different menu items match different search queries.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter the name of a menu item in the search field. | Only items matching the first query are displayed. |
| 2 | Replace the current query with another menu item name. | The updated query is displayed correctly in the search field. |
| 3 | Observe the displayed menu items. | Only items matching the updated query are displayed. Results from the previous query are no longer displayed. |

**Postcondition:** The updated search query remains applied.

---

## TC-SF-008 — Verify that special characters are handled without errors

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Negative |
| Status | Actual |

**Description:** Verify that special characters do not cause application errors or UI instability.

**Preconditions:**

- The user is on the Menu page.

**Test data:** `!@#$%^&*()`

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter special characters in the search field. | The entered characters are displayed correctly in the search field. |
| 2 | Observe the displayed menu items and page behavior. | No matching items are displayed. No application error, broken layout, or UI instability occurs. |

**Postcondition:** The entered search query remains applied.

---

## TC-SF-009 — Verify that search is case-insensitive

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the same results are returned regardless of the letter case used in the query.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item matching the test query exists.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a menu item name using lowercase letters. | Items matching the query are displayed. |
| 2 | Replace the query with the same name using uppercase letters. | The same items are displayed. |
| 3 | Replace the query with the same name using mixed-case letters. | The same items are displayed. |

**Postcondition:** Results corresponding to the entered query remain displayed.

---

## TC-SF-010 — Verify that all items matching a query are displayed

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the search displays every menu item matching the entered query.

**Preconditions:**

- The user is on the Menu page.
- At least two menu items match the same test query.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter a query that matches multiple menu items. | The entered text is displayed correctly in the search field. |
| 2 | Observe the displayed menu items. | All items matching the query are displayed. Non-matching items are hidden. |

**Postcondition:** Search results matching the entered query remain displayed.

---

## Traceability

These test cases verify the search-related requirement for the Bistro application's Menu page:

> **Menu items can be filtered using the search field.**

The test cases were designed and maintained in **Qase** and can be linked to the corresponding requirement in **Squash TM**.


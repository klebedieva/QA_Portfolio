# Category Filters — Test Cases

## Overview

This document contains functional end-to-end test cases for the category filters on the **Menu** page of the Bistro web application.

**Feature:** Menu category filtering  
**Test type:** Functional  
**Test level:** End-to-end (E2E)  
**Test design technique:** Equivalence partitioning and state transition testing  
**Tools:** Qase, Squash TM  
**Automation status:** Not automated

## Available categories

- Tout
- Entrées
- Plats
- Desserts
- Boissons

---

## TC-CF-001 — Verify that the "Tout" category is selected by default on page load

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the "Tout" category is selected by default and all available menu items are displayed when the Menu page is opened.

**Preconditions:**

- Menu items from multiple categories are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the Menu page. | The Menu page loads successfully. |
| 2 | Observe the category tabs. | The "Tout" category tab is highlighted as active by default. All other category tabs are inactive. |
| 3 | Observe the displayed menu items. | All available menu items from all categories are displayed. |

**Postcondition:** The "Tout" category remains selected.

---

## TC-CF-002 — Verify that all menu items are displayed when the "Tout" category is selected

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Tout" after another category displays all available menu items.

**Preconditions:**

- The user is on the Menu page.
- Menu items from multiple categories are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Entrées" category tab. | The "Entrées" tab becomes active, and only items from the "Entrées" category are displayed. |
| 2 | Click the "Tout" category tab. | The "Tout" category tab becomes active. |
| 3 | Observe the displayed menu items. | All available menu items from all categories are displayed. |

**Postcondition:** The "Tout" category remains selected.

---

## TC-CF-003 — Verify filtering by the "Entrées" category

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only menu items belonging to the "Entrées" category are displayed when the category is selected.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item belongs to the "Entrées" category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Entrées" category tab. | The "Entrées" category tab becomes active. |
| 2 | Observe the displayed menu items. | Only items belonging to the "Entrées" category are displayed. Items from other categories are not displayed. |

**Postcondition:** The "Entrées" category remains selected.

---

## TC-CF-004 — Verify filtering by the "Plats" category

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only menu items belonging to the "Plats" category are displayed when the category is selected.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item belongs to the "Plats" category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Plats" category tab. | The "Plats" category tab becomes active. |
| 2 | Observe the displayed menu items. | Only items belonging to the "Plats" category are displayed. Items from other categories are not displayed. |

**Postcondition:** The "Plats" category remains selected.

---

## TC-CF-005 — Verify filtering by the "Desserts" category

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only menu items belonging to the "Desserts" category are displayed when the category is selected.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item belongs to the "Desserts" category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Desserts" category tab. | The "Desserts" category tab becomes active. |
| 2 | Observe the displayed menu items. | Only items belonging to the "Desserts" category are displayed. Items from other categories are not displayed. |

**Postcondition:** The "Desserts" category remains selected.

---

## TC-CF-006 — Verify filtering by the "Boissons" category

| Field | Value |
|---|---|
| Priority | High |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only menu items belonging to the "Boissons" category are displayed when the category is selected.

**Preconditions:**

- The user is on the Menu page.
- At least one menu item belongs to the "Boissons" category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Boissons" category tab. | The "Boissons" category tab becomes active. |
| 2 | Observe the displayed menu items. | Only items belonging to the "Boissons" category are displayed. Items from other categories are not displayed. |

**Postcondition:** The "Boissons" category remains selected.

---

## TC-CF-007 — Verify that switching between categories updates the displayed items correctly

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the displayed menu items are updated correctly when switching between menu categories.

**Preconditions:**

- The user is on the Menu page.
- Menu items from multiple categories are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Entrées" category tab. | The "Entrées" tab becomes active, and only "Entrées" items are displayed. |
| 2 | Click the "Plats" category tab. | The "Plats" tab becomes active, and only "Plats" items are displayed. |
| 3 | Click the "Desserts" category tab. | The "Desserts" tab becomes active, and only "Desserts" items are displayed. |
| 4 | Click the "Boissons" category tab. | The "Boissons" tab becomes active, and only "Boissons" items are displayed. |

**Postcondition:** The "Boissons" category remains selected.

---

## TC-CF-008 — Verify that only one category tab can remain active at a time

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only one category tab remains active when switching between menu categories.

**Preconditions:**

- The user is on the Menu page.
- All category tabs are visible.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Entrées" category tab. | The "Entrées" tab becomes active. |
| 2 | Click the "Plats" category tab. | The "Plats" tab becomes active, and the "Entrées" tab becomes inactive. |
| 3 | Click the "Desserts" category tab. | The "Desserts" tab becomes active, and the "Plats" tab becomes inactive. |
| 4 | Click the "Boissons" category tab. | The "Boissons" tab becomes active, and the "Desserts" tab becomes inactive. |
| 5 | Observe all category tabs. | Only one category tab is active. |

**Postcondition:** The "Boissons" category remains active.

---

## TC-CF-009 — Verify behavior when the active category tab is clicked again

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that clicking the currently active category tab does not change the displayed items or selected category.

**Preconditions:**

- The user is on the Menu page.
- Menu items from the "Entrées" category are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the "Entrées" category tab. | The "Entrées" tab becomes active, and only items from that category are displayed. |
| 2 | Click the active "Entrées" category tab again. | The "Entrées" tab remains active, and the displayed items remain unchanged. |
| 3 | Observe the displayed menu items. | Only "Entrées" items are displayed. Items from other categories and duplicate items are not displayed. |

**Postcondition:** The "Entrées" category remains selected.

---

## Traceability

These test cases verify the Squash TM requirement:

> **Menu items can be filtered by category.**

The test cases were designed and maintained in **Qase** and linked to the corresponding requirement in **Squash TM**.


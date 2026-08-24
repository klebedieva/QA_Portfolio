# Dietary Filters — Test Cases

## Overview

This document contains functional end-to-end test cases for the dietary filters on the **Menu** page of the Bistro web application.

**Feature:** Dietary preference filtering  
**Test type:** Functional  
**Test level:** End-to-end (E2E)  
**Test design techniques:** Equivalence partitioning, decision table testing, and state transition testing  
**Combination rule:** AND — an item must satisfy every selected dietary filter  
**Tools:** Qase, Squash TM  
**Automation status:** Not automated

## Available dietary filters

- Végétarien
- Végan
- Sans gluten

---

## TC-DF-001 — Verify the default state of dietary filters

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that all dietary filters are displayed correctly and are unselected by default when the Menu page is opened.

**Preconditions:**

- Menu items matching different dietary preferences are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the Menu page. | The Menu page loads successfully. |
| 2 | Locate the dietary-filter section. | The "Végétarien", "Végan", and "Sans gluten" filters are visible and enabled. |
| 3 | Observe the state of all dietary filters. | Every dietary filter is unselected and visually inactive by default. |
| 4 | Observe the displayed menu items. | No item is hidden because of a dietary preference. |

**Postcondition:** No dietary filter is selected, and the menu remains unfiltered by dietary preference.

---

## TC-DF-002 — Verify filtering by the "Végétarien" option

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Végétarien" displays only vegetarian menu items.

**Preconditions:**

- The user is on the Menu page.
- At least one vegetarian item is available.
- At least one non-vegetarian item is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végétarien" filter. | The filter becomes selected and visually active. |
| 2 | Observe the displayed menu items. | Only items marked as vegetarian are displayed. Non-vegetarian items are hidden. |

**Postcondition:** "Végétarien" remains selected, and only vegetarian items remain displayed.

---

## TC-DF-003 — Verify filtering by the "Végan" option

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Végan" displays only vegan menu items.

**Preconditions:**

- The user is on the Menu page.
- At least one vegan item is available.
- At least one non-vegan item is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végan" filter. | The filter becomes selected and visually active. |
| 2 | Observe the displayed menu items. | Only items marked as vegan are displayed. Non-vegan items are hidden. |

**Postcondition:** "Végan" remains selected, and only vegan items remain displayed.

---

## TC-DF-004 — Verify filtering by the "Sans gluten" option

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Sans gluten" displays only gluten-free menu items.

**Preconditions:**

- The user is on the Menu page.
- At least one gluten-free item is available.
- At least one item containing gluten is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Sans gluten" filter. | The filter becomes selected and visually active. |
| 2 | Observe the displayed menu items. | Only items marked as gluten-free are displayed. Items containing gluten are hidden. |

**Postcondition:** "Sans gluten" remains selected, and only gluten-free items remain displayed.

---

## TC-DF-005 — Verify that a selected dietary filter can be cleared

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that clicking the selected "Végétarien" filter again clears it and removes the dietary restriction.

**Preconditions:**

- The user is on the Menu page.
- Vegetarian and non-vegetarian items are available.
- No other filters are applied.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végétarien" filter. | The filter becomes active, and only vegetarian items are displayed. |
| 2 | Click the selected "Végétarien" filter again. | The filter becomes unselected and visually inactive. |
| 3 | Observe the displayed menu items. | All available items are displayed again, including previously hidden non-vegetarian items. |

**Postcondition:** No dietary filter remains selected, and the menu is unfiltered by dietary preference.

---

## TC-DF-006 — Verify two dietary filters selected simultaneously

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Végétarien" and "Sans gluten" displays only items satisfying both filters.

**Preconditions:**

- The user is on the Menu page.
- At least one item matching both filters is available.
- At least one item matches only one of the selected filters.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végétarien" filter. | The filter becomes selected and visually active. |
| 2 | Select the "Sans gluten" filter. | Both filters remain selected and visually active, and the results update. |
| 3 | Observe the displayed menu items. | Only items that are both vegetarian **and** gluten-free are displayed. Items failing either condition are hidden. |

**Postcondition:** Both selected filters remain active, and only items satisfying both filters remain displayed.

> **Defect coverage:** If items matching only one selected filter are displayed, the application is applying OR logic instead of the expected AND logic; record the test as failed and link the corresponding bug report.

---

## TC-DF-007 — Verify filtering by all dietary filters

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that when all dietary filters are selected, only items satisfying every selected condition are displayed.

**Preconditions:**

- The user is on the Menu page.
- No menu item matches all three dietary filters simultaneously.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végétarien" filter. | The filter becomes selected and visually active. |
| 2 | Select the "Végan" filter. | Both filters remain active. Only items satisfying both conditions are displayed. |
| 3 | Select the "Sans gluten" filter. | All three filters remain selected and visually active, and the results update. |
| 4 | Observe the displayed menu items. | No menu item is displayed because no item satisfies all three selected conditions. |

**Postcondition:** All dietary filters remain selected, and no menu items remain displayed.

> **Defect coverage:** Displaying items that satisfy only one or two of the three conditions indicates incorrect OR logic.

---

## TC-DF-008 — Verify clearing one filter while another remains selected

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that clearing one of multiple selected dietary filters keeps the remaining filter active and updates the results accordingly.

**Preconditions:**

- The user is on the Menu page.
- At least one item matching both test filters is available.
- At least one item matches only the filter that will remain selected.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Végétarien" filter. | The filter becomes selected and visually active. |
| 2 | Select the "Sans gluten" filter. | Both filters remain active. Only items satisfying both conditions are displayed. |
| 3 | Click the selected "Sans gluten" filter again. | "Sans gluten" becomes inactive, while "Végétarien" remains active. |
| 4 | Observe the displayed menu items. | All vegetarian items are displayed, including those that are not gluten-free. Non-vegetarian items remain hidden. |

**Postcondition:** Only "Végétarien" remains selected, and the menu remains filtered accordingly.

---

## Traceability

These test cases verify the dietary-filtering requirement for the Bistro application's Menu page:

> **Menu items can be filtered by one or more dietary preferences. When multiple dietary filters are selected, an item must satisfy all selected conditions.**

The test cases were designed and maintained in **Qase** and can be linked to the corresponding requirement in **Squash TM**.


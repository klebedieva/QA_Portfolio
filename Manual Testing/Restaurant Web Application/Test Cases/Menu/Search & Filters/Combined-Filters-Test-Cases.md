# Combined Filters — Test Cases

## Overview

This document contains functional end-to-end test cases for combinations of filters on the **Menu** page of the Bistro web application.

**Feature:** Combined menu filtering  
**Test type:** Functional  
**Test level:** End-to-end (E2E)  
**Test design techniques:** Decision table testing, pairwise testing, and state transition testing  
**Combination rule:** AND — a menu item must satisfy every active criterion  
**Tools:** Qase, Squash TM  
**Automation status:** Not automated

## Filter dimensions

- Category
- Search query
- Dietary preference
- Price range

---

## TC-CMF-001 — Verify filtering by category and search query

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that menu items are filtered simultaneously by the selected category and entered search query.

**Preconditions:**

- The user is on the Menu page.
- At least one item in "Plats" matches the query `crème`.
- At least one item in another category matches the same query.
- At least one item in "Plats" does not match the query.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Plats" category. | "Plats" becomes active, and only items from this category are displayed. |
| 2 | Enter `crème` in the search field. | The query is displayed correctly in the search field. |
| 3 | Observe the displayed menu items. | Only items that belong to "Plats" **and** match `crème` are displayed. Matching items from other categories and non-matching "Plats" items are hidden. |
| 4 | Clear the search field. | The field becomes empty. "Plats" remains active, and all items from this category are displayed again. |

**Postcondition:** "Plats" remains selected, and the search field is empty.

---

## TC-CMF-002 — Verify filtering by category and dietary preference

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only items matching both the selected category and dietary filter are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one vegetarian item is available in "Entrées".
- At least one non-vegetarian item is available in "Entrées".
- At least one vegetarian item is available in another category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Entrées" category. | "Entrées" becomes active, and only items from this category are displayed. |
| 2 | Select the "Végétarien" filter. | The filter becomes active, and the results update. |
| 3 | Observe the displayed menu items. | Only vegetarian items from "Entrées" are displayed. Non-vegetarian "Entrées" items and vegetarian items from other categories are hidden. |
| 4 | Clear the "Végétarien" filter. | The dietary filter becomes inactive. "Entrées" remains selected, and all items from this category are displayed again. |

**Postcondition:** "Entrées" remains selected, and "Végétarien" is unselected.

---

## TC-CMF-003 — Verify the empty state for a combination with no matches

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Normal |
| Type | Functional / Negative |
| Status | Actual |

**Description:** Verify that an appropriate empty state is displayed when active filters return no matching menu items.

**Preconditions:**

- The user is on the Menu page.
- No item matches both the "Desserts" category and "Végan" filter.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Desserts" category. | "Desserts" becomes active, and only dessert items are displayed. |
| 2 | Select the "Végan" filter. | The filter becomes active, and the results update. |
| 3 | Observe the results area. | No menu item is displayed. An appropriate empty-state message appears, and both filters remain visibly active. |

**Postcondition:** "Desserts" and "Végan" remain selected.

---

## TC-CMF-004 — Verify filtering by category and price range

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only items matching both the selected category and price range are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one item below 15 € is available in "Plats".
- At least one item priced at 15 € or more is available in "Plats".
- At least one item below 15 € is available in another category.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Plats" category. | "Plats" becomes active, and only items from this category are displayed. |
| 2 | Select the "Moins de 15 €" price option. | The option becomes selected, and the results update. |
| 3 | Observe the displayed menu items. | Only "Plats" items priced below 15 € are displayed. More expensive "Plats" items and cheaper items from other categories are hidden. |

**Postcondition:** "Plats" and "Moins de 15 €" remain selected.

---

## TC-CMF-005 — Verify filtering by search query and price range

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only items matching both the search query and selected price range are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one item matches `crème` and is priced below 15 €.
- At least one matching item is priced at 15 € or more.
- At least one item below 15 € does not match the query.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter `crème` in the search field. | The query is displayed correctly, and matching items are shown. |
| 2 | Select the "Moins de 15 €" price option. | The price option becomes selected, and the results update. |
| 3 | Observe the displayed menu items. | Only items matching `crème` **and** priced below 15 € are displayed. Items failing either criterion are hidden. |
| 4 | Select "Tous les prix". | The price restriction is removed. All items matching `crème` are displayed again, and the query remains unchanged. |

**Postcondition:** The query remains entered, "Tous les prix" is selected, and no price restriction remains applied.

---

## TC-CMF-006 — Verify filtering by search query and dietary preference

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only items matching both the search query and selected dietary filter are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one vegetarian item matches `crème`.
- At least one non-vegetarian item matches `crème`.
- At least one vegetarian item does not match `crème`.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Enter `crème` in the search field. | The query is displayed correctly, and matching items are shown. |
| 2 | Select the "Végétarien" filter. | The filter becomes active, and the results update. |
| 3 | Observe the displayed menu items. | Only vegetarian items matching `crème` are displayed. Items failing either criterion are hidden. |
| 4 | Clear the "Végétarien" filter. | The filter becomes inactive. All items matching `crème`, including non-vegetarian items, are displayed again. |

**Postcondition:** The query remains entered, and "Végétarien" is unselected.

---

## TC-CMF-007 — Verify filtering by price range and dietary preference

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only items matching both the selected price range and dietary filter are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one vegetarian item is priced from 15 € through 25 €.
- At least one non-vegetarian item is within the same range.
- At least one vegetarian item is outside this range.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "15 € – 25 €" price option. | The option becomes selected, and only items within the inclusive range are displayed. |
| 2 | Select the "Végétarien" filter. | The filter becomes active, and the results update. |
| 3 | Observe the displayed menu items. | Only vegetarian items priced from 15 € through 25 € are displayed. Items failing either criterion are hidden. |
| 4 | Clear the "Végétarien" filter. | The filter becomes inactive. All items within the price range are displayed again, and the price option remains selected. |

**Postcondition:** "15 € – 25 €" remains selected, and "Végétarien" is unselected.

---

## TC-CMF-008 — Verify category, search, dietary, and price filters simultaneously

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that only menu items satisfying all four active filtering criteria are displayed.

**Preconditions:**

- The user is on the Menu page.
- At least one item satisfies all of the following criteria:
  - Category: "Desserts"
  - Search query: `crème`
  - Dietary preference: "Végétarien"
  - Price: below 15 €
- Items that fail at least one of these criteria are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select the "Desserts" category. | "Desserts" becomes active, and only dessert items are displayed. |
| 2 | Enter `crème` in the search field. | Only dessert items matching the query are displayed. |
| 3 | Select the "Végétarien" filter. | Only vegetarian desserts matching the query are displayed. |
| 4 | Select the "Moins de 15 €" price option. | The price option becomes selected, and the results update. |
| 5 | Observe the displayed menu items. | Only items that are desserts, match `crème`, are vegetarian, **and** cost below 15 € are displayed. Any item failing at least one criterion is hidden. |

**Postcondition:** All four filtering criteria remain applied.

> **Defect coverage:** Displaying an item that satisfies only some active criteria indicates incorrect OR logic or a failure to preserve one of the active filters.

---

## Traceability

These test cases verify the combined-filtering requirement for the Bistro application's Menu page:

> **When multiple filters are active, only menu items satisfying all applied criteria are displayed.**

The test cases were designed and maintained in **Qase** and can be linked to the corresponding requirement in **Squash TM**.


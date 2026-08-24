# Price Filters — Test Cases

## Overview

This document contains functional end-to-end test cases for the price filter on the **Menu** page of the Bistro web application.

**Feature:** Menu price filtering  
**Test type:** Functional  
**Test level:** End-to-end (E2E)  
**Test design techniques:** Equivalence partitioning, boundary value analysis, and state transition testing  
**Tools:** Qase, Squash TM  
**Automation status:** Not automated

## Price ranges

| Filter option | Applied rule |
|---|---|
| Tous les prix | No price restriction |
| Moins de 15 € | Price < 15 € |
| 15 € – 25 € | 15 € ≤ Price ≤ 25 € |
| Plus de 25 € | Price > 25 € |

---

## TC-PF-001 — Verify that "Tous les prix" is selected by default

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that "Tous les prix" is selected by default and all available menu items are displayed when the Menu page is opened.

**Preconditions:**

- Menu items with different prices are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the Menu page. | The Menu page loads successfully. |
| 2 | Observe the price filter. | "Tous les prix" is selected and visually active by default. |
| 3 | Observe the displayed menu items. | Items from all available price ranges are displayed. No price restriction is applied. |

**Postcondition:** "Tous les prix" remains selected, and all available menu items remain displayed.

---

## TC-PF-002 — Verify that all price filter options are displayed

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that the price-filter dropdown displays every available price option.

**Preconditions:**

- The user is on the Menu page.
- The price filter is visible and enabled.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Click the price-filter dropdown. | The dropdown opens, and its options are visible. |
| 2 | Observe the available options. | "Tous les prix", "Moins de 15 €", "15 € – 25 €", and "Plus de 25 €" are displayed. |
| 3 | Observe the current selection. | The selected option is visually distinguishable from the unselected options. |

**Postcondition:** The selected price option remains unchanged.

---

## TC-PF-003 — Verify the "Moins de 15 €" price filter

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that "Moins de 15 €" displays only items priced below 15 €.

**Preconditions:**

- The user is on the Menu page.
- At least one item priced below 15 € is available.
- At least one item priced at or above 15 € is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the price-filter dropdown. | The dropdown opens, and all available options are displayed. |
| 2 | Select "Moins de 15 €". | The dropdown closes, and "Moins de 15 €" is displayed as selected. |
| 3 | Observe the displayed menu items. | Only items priced below 15 € are displayed. Items priced at 15 € or more are hidden. |

**Postcondition:** "Moins de 15 €" remains selected.

---

## TC-PF-004 — Verify the "15 € – 25 €" price filter

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that "15 € – 25 €" displays only items within the selected inclusive price range.

**Preconditions:**

- The user is on the Menu page.
- Items priced within and outside the 15 €–25 € range are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the price-filter dropdown. | The dropdown opens, and all available options are displayed. |
| 2 | Select "15 € – 25 €". | The dropdown closes, and "15 € – 25 €" is displayed as selected. |
| 3 | Observe the displayed menu items. | Only items priced from 15 € through 25 €, inclusive, are displayed. Items outside this range are hidden. |

**Postcondition:** "15 € – 25 €" remains selected.

---

## TC-PF-005 — Verify the "Plus de 25 €" price filter

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that "Plus de 25 €" displays only items priced above 25 €.

**Preconditions:**

- The user is on the Menu page.
- At least one item priced above 25 € is available.
- At least one item priced at or below 25 € is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the price-filter dropdown. | The dropdown opens, and all available options are displayed. |
| 2 | Select "Plus de 25 €". | The dropdown closes, and "Plus de 25 €" is displayed as selected. |
| 3 | Observe the displayed menu items. | Only items priced above 25 € are displayed. Items priced at 25 € or less are hidden. |

**Postcondition:** "Plus de 25 €" remains selected.

---

## TC-PF-006 — Verify the boundary values of 15 € and 25 €

| Field | Value |
|---|---|
| Priority | Medium |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that items priced exactly at 15 € and 25 € are included in or excluded from the correct price ranges.

**Preconditions:**

- The user is on the Menu page.
- An item priced exactly at 15 € is available.
- An item priced exactly at 25 € is available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select "Moins de 15 €". | The 15 € item is not displayed. |
| 2 | Select "15 € – 25 €". | Both the 15 € item and the 25 € item are displayed. |
| 3 | Select "Plus de 25 €". | The 25 € item is not displayed. |

**Postcondition:** The last selected price range remains applied.

---

## TC-PF-007 — Verify that changing the price range updates the results

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that switching between price ranges dynamically updates the displayed menu items.

**Preconditions:**

- The user is on the Menu page.
- Items from all available price ranges are available.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select "Moins de 15 €". | The option becomes selected, and only items priced below 15 € are displayed. |
| 2 | Select "15 € – 25 €". | The results update. Only items priced from 15 € through 25 € are displayed; previous results are hidden. |
| 3 | Select "Plus de 25 €". | The results update. Only items priced above 25 € are displayed; previous results are hidden. |

**Postcondition:** The last selected price range remains applied.

---

## TC-PF-008 — Verify that "Tous les prix" resets the price filter

| Field | Value |
|---|---|
| Priority | High |
| Severity | Major |
| Type | Functional / Positive |
| Status | Actual |

**Description:** Verify that selecting "Tous les prix" removes the active price restriction and displays all available menu items.

**Preconditions:**

- The user is on the Menu page.
- Items from multiple price ranges are available.
- The price filter is visible and enabled.
- No other filters are applied.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Select "Moins de 15 €". | The option becomes selected, and only items priced below 15 € are displayed. |
| 2 | Select "Tous les prix". | "Tous les prix" becomes selected, and the previous price restriction is removed. |
| 3 | Observe the displayed menu items. | All available menu items are displayed again. |

**Postcondition:** "Tous les prix" remains selected, and no price restriction remains applied.

---

## Traceability

These test cases verify the price-filtering requirement for the Bistro application's Menu page:

> **Menu items can be filtered by price range.**

The test cases were designed and maintained in **Qase** and can be linked to the corresponding requirement in **Squash TM**.


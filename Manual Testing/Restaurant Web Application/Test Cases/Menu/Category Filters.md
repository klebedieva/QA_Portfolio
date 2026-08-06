# Category Filters

## Overview

This test suite verifies category-based filtering, active tab behavior, empty results, and interactions with search and dietary filters in the restaurant menu.

**Total test cases:** 13  
**Testing type:** Functional E2E testing  
**Automation status:** Manual

---

## Test Cases

### BTD-3 — Verify that all menu items are displayed when the "Tout" category is selected

**Description**  
This test case verifies that the selected "Tout" category displays all available menu items regardless of category.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- Menu items from multiple categories are available.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Entrées` category tab. | — | Only items from Entrées category are displayed. |
| 2 | Click the `Tout` category tab. | — | The Tout category tab becomes highlighted as active. |
| 3 | Observe the displayed menu items. | — | All available menu items from all categories are displayed. |

---

### BTD-4 — Verify that only items from the "Entrées" category are displayed when the category is selected

**Description**  
This test case verifies that the product catalog displays only items belonging to the "Entrées" category after the corresponding filter is selected.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- At least one menu item belongs to the "Entrées" category.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Entrées` category tab. | — | The Entrées category tab becomes highlighted as active. |
| 2 | Observe the displayed menu items. | — | Only menu items belonging to the Entrées category are displayed. Items from other categories are hidden. |

---

### BTD-5 — Verify that only items from the "Plats" category are displayed when the category is selected

**Description**  
This test case verifies that the product catalog displays only items belonging to the "Plats" category after the corresponding filter is selected.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- At least one menu item belongs to the "Plats" category.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Plats` category tab. | — | The Plats category tab becomes highlighted as active. |
| 2 | Observe the displayed menu items. | — | Only menu items belonging to the Plats category are displayed. Items from other categories are hidden. |

---

### BTD-6 — Verify that only items from the "Desserts" category are displayed when the category is selected

**Description**  
This test case verifies that the product catalog displays only items belonging to the "Desserts" category after the corresponding filter is selected.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- At least one menu item belongs to the "Desserts" category.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Desserts` category tab. | — | The Desserts category tab becomes highlighted as active. |
| 2 | Observe the displayed menu items. | — | Only menu items belonging to the Desserts category are displayed. Items from other categories are hidden. |

---

### BTD-7 — Verify that only items from the "Boissons" category are displayed when the category is selected

**Description**  
This test case verifies that the product catalog displays only items belonging to the "Boissons" category after the corresponding filter is selected.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- At least one menu item belongs to the "Boissons" category.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Boissons` category tab. | — | The Boissons category tab becomes highlighted as active. |
| 2 | Observe the displayed menu items. | — | Only menu items belonging to the Boissons category are displayed. Items from other categories are hidden. |

---

### BTD-8 — Verify that switching between categories updates the displayed items correctly

**Description**  
This test case verifies that the product catalog refreshes the displayed menu items correctly when the user switches between category filters.

**Test attributes**

- **Priority:** Medium
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- Menu items from multiple categories are available.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Entrées` category tab. | — | The Entrées category tab becomes highlighted as active. |
| 2 | Observe the displayed items. | — | Only menu items belonging to the Entrées category are displayed. Items from other categories are hidden. |
| 3 | Click the `Plats` category tab. | — | The Plats category tab becomes highlighted as active. |
| 4 | Observe the displayed items. | — | Only menu items belonging to the Plats category are displayed. Items from other categories are hidden. |
| 5 | Click the `Desserts` category tab. | — | The Desserts category tab becomes highlighted as active. |
| 6 | Observe the displayed items. | — | Only menu items belonging to the Desserts category are displayed. Items from other categories are hidden. |
| 7 | Click the `Boissons` category tab. | — | The Boissons category tab becomes highlighted as active. |
| 8 | Observe the displayed items. | — | Only menu items belonging to the Boissons category are displayed. Items from other categories are hidden. |

---

### BTD-9 — Verify that only one category tab can remain active at a time

**Description**  
This test case verifies that category filter navigation maintains a single active state and does not allow multiple category tabs to appear selected simultaneously.

**Test attributes**

- **Priority:** Medium
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- Category filter tabs are visible.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the `Entrées` category tab. | — | The Entrées category tab becomes highlighted as active. |
| 2 | Click the `Plats` category tab. | — | The Plats category tab becomes active and the Entrées tab is no longer active. |
| 3 | Click the `Desserts` category tab. | — | The Desserts category tab becomes active and the Plats tab is no longer active. |
| 4 | Click the `Boissons` category tab. | — | The Boissons category tab becomes active and the Desserts tab is no longer active. |
| 5 | Observe the category tabs. | — | Only one category tab is highlighted as active at a time. |

---

### BTD-10 — Verify category filter behavior when a selected category contains no items

**Description**  
This test case verifies system behavior when the user selects a category for which no menu items are currently available.

**Test attributes**

- **Priority:** Medium
- **Severity:** Normal
- **Behavior:** Negative
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- A category exists in the system without any assigned menu items.

**Postconditions**

- User remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click a category tab that contains no menu items. | — | The selected category tab becomes highlighted as active. |
| 2 | Observe the product catalog area. | — | No menu items are displayed for the selected category. |
| 3 | Observe the page layout. | — | The page layout remains stable and no UI errors are displayed. |

---

### BTD-21 — Verify that the "Tout" category is selected by default when the Menu page is opened

**Description**  
This test case verifies that the "Tout" category is selected by default and all available menu items are displayed when the user opens the Menu page.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- Menu items from multiple categories are available.
- The user has not selected any category during the current session.

**Postconditions**

- The user remains on the Menu page.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Open the Menu page. | — | The Menu page is displayed successfully. |
| 2 | Observe the category tabs. | — | The "Tout" category tab is highlighted as active by default. All other category tabs are displayed as inactive. |
| 3 | Observe the displayed menu items. | — | All available menu items from all categories are displayed. |

---

### BTD-22 — Verify category filter behavior when the currently active category tab is clicked again

**Description**  
This test case verifies that clicking an already selected category tab does not reset the filter, duplicate menu items or cause an incorrect page state.

**Test attributes**

- **Priority:** Medium
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- Menu items from the Entrées category are available.

**Postconditions**

- The "Entrées" category remains selected.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the "Entrées" category tab. | — | The "Entrées" category tab becomes highlighted as active.<br>Only items from the Entrées category are displayed. |
| 2 | Click the active "Entrées" category tab again. | — | The "Entrées" category tab remains highlighted as active.<br>The category filter remains applied. |
| 3 | Observe the displayed menu items. | — | Only items from the Entrées category are displayed.<br>No items are duplicated, removed unexpectedly or displayed from other categories. |

---

### BTD-23 — Verify that menu items are filtered by both the selected category and the search query

**Description**  
This test case verifies that menu items are filtered simultaneously by the selected category and the entered search query.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- The Menu contains multiple items from different categories.
- At least one item in the Plats category matches the test search query.
- At least one item from another category also matches or partially matches the search query.

**Postconditions**

- The selected category and search query remain applied.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the "Plats" category tab. | — | The "Plats" category tab becomes highlighted as active.<br>Only items from the Plats category are displayed. |
| 2 | Enter a valid menu item name in the search field. | `spaghettis` | The search query is entered successfully. |
| 3 | Observe the displayed menu items. | — | Only items that belong to the Plats category and match the entered search query are displayed.<br>Items from other categories are not displayed.<br>Non-matching items from the Plats category are not displayed. |
| 4 | Clear the search field. | — | All available items from the Plats category are displayed again.<br>The "Plats" category remains selected. |

---

### BTD-24 — Verify that menu items are filtered by both the selected category and the selected dietary filter

**Description**  
This test case verifies that only menu items matching both the selected category and the selected dietary filter are displayed.

**Test attributes**

- **Priority:** High
- **Severity:** Normal
- **Behavior:** Positive
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- Menu items from multiple categories are available.
- At least one vegetarian item is available in the Plats category.
- At least one non-vegetarian item is available in the Plats category.

**Postconditions**

- The "Plats" category and "Végétarien" filter remain selected.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the "Plats" category tab. | — | The "Plats" category tab becomes highlighted as active.<br>Only items from the Plats category are displayed. |
| 2 | Select the "Végétarien" filter. | — | The "Végétarien" filter becomes active. |
| 3 | Observe the displayed menu items. | — | Only vegetarian items belonging to the Plats category are displayed.<br>Non-vegetarian items are not displayed.<br>Items from other categories are not displayed. |
| 4 | Clear the "Végétarien" filter. | — | All available items from the Plats category are displayed again.<br>The "Plats" category remains selected. |

---

### BTD-25 — Verify that no menu item cards are displayed when no items match the selected category and filters

**Description**  
This test case verifies the interface behavior when no menu items match the selected category and additional filter criteria.

**Test attributes**

- **Priority:** Medium
- **Severity:** Normal
- **Behavior:** Negative
- **Type:** Functional
- **Layer:** E2E
- **Automation status:** Manual

**Preconditions**

- User is on the Menu page.
- A category and filter combination that produces no matching menu items is available.

**Postconditions**

- The selected category and dietary filter remain active.

| Step | Action | Input Data | Expected Result |
|---:|---|---|---|
| 1 | Click the "Desserts" category tab. | — | The "Desserts" category tab becomes highlighted as active.<br>Dessert items are displayed. |
| 2 | Select the "Végan" filter. | — | The "Végan" filter becomes active. |
| 3 | Observe the menu item area. | — | No menu item cards are displayed.<br>The selected filters remain applied.<br>The page remains functional. |

---

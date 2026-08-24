# BUG-004 — Multiple dietary filters use OR logic instead of AND logic

| Field | Value |
|---|---|
| Qase defect ID | 5 |
| Severity | Major |
| Priority | High |
| Status | Open |
| Feature | Dietary Filters |
| Reported by | Karyna Lebedieva |

## Description

When several dietary filters are selected, the application displays items matching any selected condition instead of requiring every condition to be satisfied.

## Preconditions

- The user is on the Menu page.
- No menu item matches "Végétarien", "Végan", and "Sans gluten" simultaneously.

## Steps to reproduce

1. Open the Menu page.
2. Select the "Végétarien" filter.
3. Select the "Végan" filter.
4. Select the "Sans gluten" filter.
5. Observe the displayed menu items.

## Actual result

Items matching at least one selected dietary filter are displayed. As a result, all available menu items remain visible even though no item matches all three filters.

## Expected result

Only items matching all selected dietary filters are displayed. Since no item satisfies all three conditions, no menu item is displayed and an appropriate empty-state message appears.

## Related test cases

- `TC-DF-006 — Verify two dietary filters selected simultaneously`
- `TC-DF-007 — Verify filtering by all dietary filters`
- `TC-CMF-008 — Verify category, search, dietary, and price filters simultaneously`


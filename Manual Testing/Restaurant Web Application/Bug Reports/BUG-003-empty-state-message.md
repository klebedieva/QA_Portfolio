# BUG-003 — Empty-state message is not displayed when filters return no matching items

| Field | Value |
|---|---|
| Qase defect ID | 4 |
| Severity | Normal |
| Priority | Medium |
| Status | Open |
| Feature | Combined Filters / Empty State |
| Reported by | Karyna Lebedieva |

## Description

The application displays a blank results area instead of informing the user that the active filters returned no matches.

## Preconditions

- The user is on the Menu page.
- No item matches both the "Desserts" category and "Végan" dietary filter.

## Steps to reproduce

1. Open the Menu page.
2. Select the "Desserts" category.
3. Select the "Végan" dietary filter.
4. Observe the results area.

## Actual result

No menu item is displayed, but no empty-state message is shown.

## Expected result

An appropriate empty-state message informs the user that no matching menu items were found.

## Evidence

[View the screenshot attached to the Qase report](https://d2cxucsjd6xvsd.cloudfront.net/public/team/5b86af54b45a1f3fd7588688c080e099920a0452/attachment/e8f408208299d7c4ebd227914a01887a4ea77616/image.png)

## Related test case

`TC-CMF-003 — Verify the empty state for a combination with no matches`


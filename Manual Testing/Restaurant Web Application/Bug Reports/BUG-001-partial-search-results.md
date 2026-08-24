# BUG-001 — Search returns unrelated menu items for a partial keyword

| Field | Value |
|---|---|
| Qase defect ID | 1 |
| Severity | Normal |
| Priority | Medium |
| Status | Open |
| Feature | Menu Search |
| Reported by | Karyna Lebedieva |

## Description

Entering a partial keyword returns a menu item that is not relevant to the intended search query.

## Preconditions

- The user is on the Menu page.
- The search field is visible and enabled.

## Test data

`boulette`

## Steps to reproduce

1. Open the Menu page.
2. Enter `boulette` in the search field.
3. Observe the displayed search results.

## Actual result

A menu item containing the word "ciboulette" in its description is displayed, even though it is not relevant to the entered keyword `boulette`.

## Expected result

Only menu items relevant to the entered search query are displayed. Unrelated menu items do not appear in the results.

## Evidence

[View the screenshot attached to the Qase report](https://d2cxucsjd6xvsd.cloudfront.net/public/team/5b86af54b45a1f3fd7588688c080e099920a0452/attachment/7da30232d334ba4fbf01945c375d5fced8b1dbb1/image.png)

## Related test case

`TC-SF-003 — Verify filtering by a partial search query`


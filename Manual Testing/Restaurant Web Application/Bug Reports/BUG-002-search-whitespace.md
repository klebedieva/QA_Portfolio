# BUG-002 — Search does not handle leading and trailing whitespace correctly

| Field | Value |
|---|---|
| Qase defect ID | 2 |
| Severity | Minor |
| Priority | Low |
| Status | Open |
| Feature | Menu Search |
| Reported by | Karyna Lebedieva |

## Description

A valid menu item is not found when its name is entered with leading or trailing spaces.

## Preconditions

- The user is on the Menu page.
- A menu item matching the trimmed query exists.
- The search field is visible and enabled.

## Steps to reproduce

1. Open the Menu page.
2. Enter a valid menu item name with one or more leading or trailing spaces.
3. Observe the search results.

## Actual result

No matching menu item is displayed when the query contains leading or trailing whitespace.

## Expected result

The search ignores leading and trailing whitespace and displays the menu items matching the trimmed query.

## Evidence

[View the screenshot attached to the Qase report](https://d2cxucsjd6xvsd.cloudfront.net/public/team/5b86af54b45a1f3fd7588688c080e099920a0452/attachment/8b6cdaa351960dae9c4adaa7d62dd13c88cd7cd8/bug_BTD16.png)

## Related test case

`TC-SF-006 — Verify that leading and trailing spaces are ignored`


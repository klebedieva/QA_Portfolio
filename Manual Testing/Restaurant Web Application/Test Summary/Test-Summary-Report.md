# Test Summary Report

## 1. Project information

| Field | Details |
|---|---|
| Project | Bistro Web Application |
| Application URL | https://bistro-template.onrender.com |
| Tested area | Menu page |
| Test type | Functional testing |
| Test level | End-to-end (E2E) |
| Test management tools | Qase, Squash TM |
| Test execution date | 24 August 2026 |
| Tester | Karyna Lebedieva |

## 2. Objective

The objective of this testing cycle was to validate the Menu page filtering functionality and verify that menu items are displayed correctly according to the user's selected criteria.

The testing focused on individual filters, transitions between filter states, boundary values, negative scenarios, and combinations of multiple filters.

## 3. Scope

### In scope

- Category filters
- Search functionality
- Price filters
- Dietary filters
- Combined filters
- Empty-state behavior
- Resetting and clearing filters
- Boundary values for price ranges
- AND logic for simultaneously applied filters

### Out of scope

- Cart functionality
- Checkout process
- Reservation functionality
- Contact form
- API testing
- Performance testing
- Security testing
- Cross-browser and mobile compatibility testing
- Automated testing

## 4. Test execution summary

| Metric | Result |
|---|---:|
| Total test cases | 43 |
| Executed | 43 |
| Passed | 39 |
| Failed | 4 |
| Blocked | 0 |
| Not executed | 0 |
| Pass rate | 90.7% |
| Fail rate | 9.3% |

## 5. Results by test suite

| Test suite | Total | Passed | Failed | Pass rate |
|---|---:|---:|---:|---:|
| Category Filters | 9 | 9 | 0 | 100% |
| Search Filters | 10 | 8 | 2 | 80% |
| Price Filters | 8 | 8 | 0 | 100% |
| Dietary Filters | 8 | 7 | 1 | 87.5% |
| Combined Filters | 8 | 7 | 1 | 87.5% |
| **Total** | **43** | **39** | **4** | **90.7%** |

## 6. Failed test cases

| Test case | Related defect | Result |
|---|---|---|
| TC-SF-003 — Verify filtering by a partial search query | BUG-001 — Search returns unrelated menu items for a partial keyword | Failed |
| TC-SF-006 — Verify that leading and trailing spaces are ignored | BUG-002 — Search does not handle leading and trailing whitespace | Failed |
| TC-CMF-003 — Verify the empty state for a combination with no matches | BUG-003 — Empty-state message is not displayed | Failed |
| TC-DF-007 — Verify filtering by all dietary filters | BUG-004 — Multiple dietary filters use OR logic instead of AND logic | Failed |

## 7. Defect summary

| ID | Defect | Severity | Priority | Status |
|---|---|---|---|---|
| BUG-001 | Search returns unrelated menu items for a partial keyword | Normal | Medium | Open |
| BUG-002 | Search does not handle leading and trailing whitespace | Minor | Low | Open |
| BUG-003 | Empty-state message is not displayed when filters return no matching items | Normal | Medium | Open |
| BUG-004 | Multiple dietary filters use OR logic instead of AND logic | Major | High | Open |

### Defects by severity

| Severity | Count |
|---|---:|
| Major | 1 |
| Normal | 2 |
| Minor | 1 |
| **Total** | **4** |

All identified defects remain open at the end of the testing cycle.

## 8. Key findings

- Category filtering works correctly for all available categories.
- Price filtering works correctly, including the boundary values of 15 € and 25 €.
- The default states and reset behavior of the tested filters work as expected.
- Search results are affected by leading and trailing whitespace.
- A partial keyword can return an unrelated menu item because the keyword appears inside another word in the description.
- The application does not display an informative empty-state message when a filter combination returns no results.
- Multiple dietary filters use OR logic instead of the expected AND logic. This is the most significant defect because it changes the meaning of the selected filtering criteria.

## 9. Risks and limitations

- Users may receive inaccurate dietary filtering results when multiple dietary preferences are selected.
- The absence of an empty-state message may make a blank results area appear to be a loading or application error.
- Search input is not normalized before filtering, which reduces search reliability.
- Testing was limited to the Menu page and does not provide quality conclusions for the rest of the application.
- Cross-browser, responsive, accessibility, API, performance, and security testing were not included in this cycle.

## 10. Recommendations

1. Replace OR logic with AND logic when multiple dietary filters are selected.
2. Add a clear empty-state message when no menu items match the active criteria.
3. Trim leading and trailing whitespace before processing a search query.
4. Review the partial-search matching rules to prevent unrelated results.
5. Retest all four failed scenarios after fixes are implemented.
6. Run regression testing for Category, Search, Dietary, Price, and Combined Filters after the defects are resolved.

## 11. Exit criteria evaluation

| Criterion | Status |
|---|---|
| All planned test cases executed | Met |
| Test results documented | Met |
| Identified defects documented | Met |
| No open major defects | Not met |
| Failed scenarios successfully retested | Not met |

## 12. Conclusion

All 43 planned test cases were executed. Of these, 39 passed and 4 failed, resulting in a pass rate of **90.7%**.

The core category and price-filtering functionality works as expected. However, the Menu page does not fully satisfy the expected filtering behavior because four defects remain open, including one major defect affecting the logic of multiple dietary filters.

The tested functionality can be considered **partially successful but not ready for final acceptance**. The identified defects should be fixed and the affected scenarios should be retested before the Menu filtering feature is approved.


# Restaurant Web Application — Test Plan

**Document version:** 1.1  
**Project:** Bistro Restaurant Web Application  
**Application URL:** https://bistro-template.onrender.com  
**Prepared for:** QA Portfolio  
**Testing approach:** Manual functional testing  

---

## 1. Introduction

This document defines the test plan for the Bistro Restaurant Web Application.

The application allows users to:

- Browse restaurant information
- View the menu
- Search and filter menu items
- View detailed dish information
- Review ingredients, allergens, preparation details, nutrition information, and dish reviews
- View similar dishes
- Add dishes to a shopping cart
- Update or remove cart items
- Choose home delivery or restaurant pickup
- Enter customer and delivery information
- Select a delivery or pickup date and time
- Choose a payment method for payment upon receipt
- Apply a promotional code
- Review and confirm an order
- Submit a table reservation
- View customer reviews
- Submit a customer review
- Load additional customer reviews
- Send a contact request
- Browse and filter the restaurant gallery

The purpose of testing is to verify that the application's main user flows work correctly, that calculations and validations are accurate, and that users can complete reservations, reviews, and orders without functional errors.

---

## 2. Test Objectives

The main objectives are to:

- Verify that all public pages load successfully.
- Validate navigation between application pages.
- Verify menu item presentation and categorization.
- Validate search and filter behavior.
- Verify detailed dish information, including ingredients, allergens, preparation, nutrition, reviews, and similar dishes.
- Verify shopping cart functionality.
- Validate price, tax, delivery fee, discount, and total calculations.
- Verify the checkout flow from cart review to order confirmation.
- Validate delivery and pickup options.
- Verify customer information and address form validation.
- Verify reservation form functionality.
- Verify customer review display and submission functionality.
- Verify loading of additional reviews and navigation from the reviews page.
- Verify contact form functionality.
- Validate gallery filtering and image display.
- Verify that the application provides appropriate feedback for successful and unsuccessful user actions.
- Identify functional, UI, and usability defects before release.

---

## 3. Scope

### 3.1 Features in Scope

The following application areas are included in testing:

#### Home Page

- Header and navigation
- Hero carousel or banner
- Call-to-action buttons
- Restaurant introduction
- Customer review preview section
- "Add Review" button
- "View All Reviews" button
- Gallery preview
- Reservation preview
- Footer

#### Navigation

- Logo navigation
- Header links
- Active page indication
- Navigation to Home, Menu, Gallery, Contact, Reservation, Reviews, and Cart
- Breadcrumb navigation
- Navigation using call-to-action buttons
- Footer links

#### Menu

- Menu page loading
- Menu section display
- Product card layout
- Product names, descriptions, prices, and badges
- Product details access
- Category sections
- Beverage list
- Add-to-cart buttons

#### Category Filters

- Default category state
- Tout
- Entrées
- Plats
- Desserts
- Boissons
- Switching between categories
- Single active category behavior
- Empty category behavior
- Combined category filtering

#### Search Filter

- Default search field state
- Exact search
- Partial search
- Case-insensitive search
- Search result updates
- No matching results
- Search field clearing
- Leading and trailing spaces
- Queries containing only spaces
- Special characters
- Multiple matching results

#### Price Filter

- Default price filter state
- Tous les prix
- Moins de 15€
- 15€ - 25€
- Plus de 25€
- Boundary values
- Switching between price ranges
- Resetting the price filter
- No matching results
- Combined filtering with categories and other filters

#### Dietary Filters

- Végétarien
- Végan
- Sans gluten
- Selecting and clearing filters
- Multiple dietary filters
- Combined dietary, category, search, and price filters
- Empty result behavior

#### Dish Details

- Dish details page loading
- Breadcrumb navigation
- Dish image
- Dish name
- Description
- Price
- Average rating
- Review count
- Category and dietary badges
- Ingredient list
- Allergen list
- Quantity increase and decrease controls
- Minimum quantity behavior
- Adding the selected quantity to the cart
- Preparation tab
- Nutrition tab
- Reviews tab
- Preparation time
- Chef recommendation
- Dish-specific customer reviews
- Similar dishes section
- Navigation to a similar dish
- Consistency between menu card data and dish details

#### Customer Reviews

- Customer review preview on the Home page
- Full reviews page loading
- Reviews hero section
- Breadcrumb display
- "Add Your Review" button
- Customer name
- Review date
- Rating value
- Star display
- Review text
- Review card layout
- Loading additional reviews
- End-of-list behavior
- Navigation to Menu from the reviews page
- Navigation to Reservation from the reviews page
- Review submission form
- Required field validation
- Rating selection
- Review text validation
- Successful review submission
- Error feedback
- Display of a newly submitted review, if supported
- Dish-specific review display on the dish details page

#### Shopping Cart

- Adding one item
- Adding multiple different items
- Increasing quantity
- Decreasing quantity
- Preventing invalid quantities
- Removing an item
- Clearing the cart
- Cart counter updates
- Cart drawer opening and closing
- Item name, quantity, unit price, and line total
- Cart total calculation
- Proceeding to checkout
- Empty cart behavior
- Cart state during the current session

#### Checkout — Cart Review

- Display of selected items
- Quantity updates
- Item removal
- Subtotal calculation
- VAT calculation
- Delivery fee display
- Total calculation
- Promo code field
- Continue shopping
- Continue to next checkout step
- Checkout progress indicator

#### Checkout — Delivery and Pickup

- Home delivery option
- Restaurant pickup option
- Delivery fee application
- Free pickup
- Conditional display of delivery address fields
- Address input
- Postal code input
- Optional delivery instructions
- First name
- Last name
- Phone number
- Email address
- Date selection
- Time slot selection
- Required-field validation
- Email format validation
- Phone format validation
- Prevention of past date selection
- Preservation of data when navigating back

#### Checkout — Payment Method

The website does not process online payments.

The following payment methods are selected for payment upon delivery or pickup:

- Bank card
- Cash
- Restaurant vouchers

Testing includes:

- Selecting each payment method
- Ensuring only one payment method is active
- Preserving the selected method
- Displaying the selected method in the order review
- Navigating forward and backward in the checkout flow

#### Promotional Code

- Empty promo code
- Valid promo code, if test data is available
- Invalid promo code
- Discount calculation
- Total recalculation
- Reapplying or removing a promo code, if supported

#### Order Review and Confirmation

- Ordered items
- Quantities and prices
- Customer information
- Delivery or pickup method
- Date and time
- Payment method
- VAT and total amount
- Terms and conditions checkbox
- Prevention of confirmation without accepting terms
- Successful order submission
- Order number generation
- Success message
- Final total
- Return to menu
- Cart reset after successful confirmation

#### Reservation

- Reservation page loading
- First name
- Last name
- Email
- Phone number
- Date
- Time
- Number of guests
- Optional message
- Required-field validation
- Email and phone format validation
- Date and time validation
- Maximum number of guests
- Successful reservation submission
- Success and error feedback

#### Contact

- Contact information display
- First name
- Last name
- Email
- Phone number
- Subject selection
- Message
- Consent checkbox
- Required-field validation
- Email and phone format validation
- Successful form submission
- Error feedback
- Embedded map
- Opening hours

#### Gallery

- Gallery page loading
- Image display
- Gallery category filters
- Tout
- Terrasse
- Intérieur
- Plats
- Ambiance
- Switching filters
- Empty filter results
- Image layout and responsiveness
- "View Full Gallery" navigation

#### Footer

- Restaurant information
- Opening hours
- Phone and email links
- Social media links
- Administration link
- Legal notice
- Privacy policy
- Cookie settings

---

## 4. Features Out of Scope

The following areas are not included in this test plan:

- Online payment processing
- Payment gateway integration
- Bank card authorization
- Real financial transactions
- Refund processing
- Production database validation
- Source code review
- Penetration testing
- Security vulnerability assessment
- Load testing
- Stress testing
- Large-scale performance testing
- Full accessibility compliance audit
- Native mobile application testing
- Third-party service internals
- Restaurant staff order management, unless administrative access is provided
- Review moderation workflow, unless administrative access is provided
- Email delivery infrastructure, unless a test mailbox is available
- Real delivery logistics

---

## 5. Test Approach

Testing will be primarily manual and risk-based.

The following test types will be performed:

### Functional Testing

Verify that features behave according to expected business rules.

### UI Testing

Verify layout, labels, buttons, fields, visual states, review stars, tabs, and feedback messages.

### Smoke Testing

Verify that critical pages and primary user flows are available after deployment.

### Regression Testing

Re-execute affected and critical test cases after defect fixes or changes.

### Exploratory Testing

Investigate unexpected behavior, edge cases, and usability issues not fully covered by scripted tests.

### Cross-Browser Testing

Verify core functionality in supported browsers.

### Negative Testing

Verify validation and error handling using invalid, incomplete, or unsupported input.

### Boundary Value Testing

Verify limits such as price ranges, quantities, dates, guest counts, rating values, and field lengths.

### End-to-End Testing

Verify complete flows such as:

- Browse menu → open dish details → select quantity → add item → cart → checkout → confirmation
- Open reviews page → load additional reviews → submit a review
- Open reservation page → complete form → submit reservation
- Open contact page → complete form → submit message

---

## 6. Test Environment

### Application

- **Application:** Bistro Restaurant Web Application
- **Environment:** Public staging/demo environment
- **URL:** https://bistro-template.onrender.com

### Desktop Environment

- **Operating system:** Windows 11
- **Primary browser:** Google Chrome
- **Additional browsers:** Microsoft Edge and Mozilla Firefox
- **Recommended resolution:** 1920 × 1080
- **Secondary resolution:** 1366 × 768

### Optional Responsive Checks

Where time permits:

- Tablet viewport
- Mobile viewport
- Browser zoom behavior

### External Dependencies

- Google Maps
- Hosting environment
- Email service, if enabled
- Backend order, reservation, contact, and review services

---

## 7. Test Data

Test data should include:

### Menu and Dish Data

- Items from every category
- Items below 15€
- Items priced exactly at 15€
- Items between 15€ and 25€
- Items priced exactly at 25€
- Items above 25€
- Vegetarian items
- Vegan items
- Gluten-free items
- Items with allergens
- Items with multiple ingredients
- Items with nutrition data
- Items with preparation information
- Items with reviews
- Items without reviews, if available
- Items with similar dish recommendations
- Items matching multiple search queries
- Category/filter combinations with no matching items

### Review Data

- Ratings from 1 to 5 stars
- Valid reviewer names
- Valid review text
- Empty required fields
- Minimum and maximum review lengths
- Existing reviews with different ratings and dates
- Sufficient review records to test "Load More"
- Dish-specific reviews

### Customer Data

- Valid French names
- Valid and invalid email addresses
- Valid and invalid French phone numbers
- Valid and invalid postal codes
- Delivery and pickup scenarios

### Order Data

- Single item
- Multiple different items
- Multiple quantities of one item
- Delivery order
- Pickup order
- Each supported payment method
- Valid and invalid promo codes, if available

### Reservation Data

- Valid future date
- Invalid past date
- Available time slot
- Minimum and maximum guest counts
- Required and optional message data

---

## 8. Entry Criteria

Testing may begin when:

- The application is deployed and accessible.
- Main pages load without blocking server errors.
- Required test data is available.
- Core backend services are reachable.
- The current build is identified.
- Known critical deployment issues are documented.
- Test environment credentials are available, if required.
- Business rules or accepted assumptions are available for unclear behavior.

---

## 9. Exit Criteria

Testing is considered complete when:

- All planned high-priority test cases have been executed.
- Critical user flows have passed.
- No open Critical defects remain.
- No unresolved High-severity defects block core functionality.
- Medium- and Low-severity defects are documented and accepted or planned.
- Regression testing has been completed after fixes.
- Test execution results are documented.
- A Test Summary Report has been prepared.
- Known limitations and residual risks are recorded.

---

## 10. Suspension and Resumption Criteria

### Testing may be suspended when:

- The application is unavailable.
- A blocking defect prevents access to major modules.
- Test data is missing or corrupted.
- Backend services are unavailable.
- A new deployment invalidates ongoing execution.

### Testing may resume when:

- The blocking issue is resolved.
- The environment becomes stable.
- Required data is restored.
- The affected build is redeployed and identified.

---

## 11. Defect Management

Defects will be documented with:

- Unique defect ID
- Clear title
- Environment
- Preconditions
- Reproduction steps
- Expected result
- Actual result
- Severity
- Priority
- Screenshots or video
- Status
- Related test case

### Suggested Severity Levels

- **Critical:** Complete application or order flow is unavailable; data loss or unrecoverable failure.
- **High:** Major business function is broken and no acceptable workaround exists.
- **Normal:** Feature works incorrectly but a workaround exists or impact is limited.
- **Minor:** Cosmetic, content, or low-impact usability issue.

---

## 12. Test Deliverables

The following deliverables will be produced:

- Test Plan
- Manual Test Cases
- Test Suites
- Bug Reports
- Screenshots and supporting evidence
- Test Execution Results
- Regression Results
- Test Summary Report
- GitHub QA Portfolio Documentation

---

## 13. Roles and Responsibilities

### Manual QA Engineer

Responsibilities include:

- Reviewing application behavior
- Identifying test conditions
- Designing test cases
- Preparing test data
- Executing tests
- Reporting defects
- Retesting fixes
- Performing regression testing
- Maintaining test documentation
- Preparing the Test Summary Report

### Developer

Expected responsibilities include:

- Providing deployable builds
- Investigating reported defects
- Implementing fixes
- Clarifying technical behavior
- Supporting defect reproduction

### Product Owner or Project Stakeholder

Expected responsibilities include:

- Clarifying business requirements
- Confirming expected behavior
- Prioritizing defects
- Accepting residual risks
- Approving release readiness

---

## 14. Risks and Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| Incomplete or undocumented requirements | Expected results may be unclear | Record assumptions and request clarification |
| Public demo environment instability | Test execution may be interrupted | Retest when stable and document outages |
| Test data changes | Existing test cases may become invalid | Use explicit test data and update cases when needed |
| Third-party map or email service failure | Contact-related checks may fail | Separate third-party failure from application failure |
| Review data or moderation behavior is unclear | Review submission results may be ambiguous | Document assumptions and verify expected workflow |
| Browser-specific behavior | Functionality may differ by browser | Execute critical flows in Chrome, Edge, and Firefox |
| Limited testing time | Lower-risk scenarios may remain untested | Prioritize critical business flows |
| No real online payment | Payment processing cannot be validated | Test only payment method selection for payment upon receipt |
| Promo code data unavailable | Positive promo-code test may be blocked | Execute negative tests and mark positive case as blocked |
| Backend confirmation without visible admin access | Order, reservation, or review persistence cannot be fully verified | Verify confirmation UI and request backend evidence if available |

---

## 15. Assumptions

This test plan is based on the following assumptions:

- The application is a public restaurant ordering and reservation website.
- Users do not need to register or sign in.
- Orders can be placed as a guest.
- Reviews can be viewed without authentication.
- Review submission is available to guest users unless otherwise restricted.
- Payment is completed upon delivery or pickup.
- No online payment transaction occurs on the website.
- Home delivery includes a delivery fee.
- Restaurant pickup is free.
- The application supports a maximum of 20 reservation guests, based on displayed information.
- Only future dates should be accepted for reservations and orders.
- Order, reservation, contact, and review submission services are available in the test environment.
- The cart is expected to preserve data during the active browser session.
- French is the primary interface language.
- Tax is calculated using the rate displayed by the application.
- Average dish ratings and review counts should match the underlying displayed reviews.
- Where requirements are absent, current consistent behavior will be documented and reviewed before being treated as expected behavior.

---

## 16. Priority of Critical User Flows

The following flows have the highest testing priority:

1. Open Menu page
2. Search and filter menu items
3. Open a dish details page
4. Verify ingredients, allergens, preparation, nutrition, and reviews
5. Select quantity and add an item to the cart
6. Update quantity and verify totals
7. Choose delivery or pickup
8. Enter customer information
9. Select date, time, and payment method
10. Accept terms and confirm the order
11. Verify order confirmation and order number
12. Open the Reviews page and load additional reviews
13. Submit a valid customer review
14. Submit a valid reservation
15. Submit a valid contact request

---

## 17. Approval

| Role | Name | Status |
|---|---|---|
| Manual QA Engineer | To be completed | Draft |
| Developer | To be completed | Pending |
| Product Owner / Stakeholder | To be completed | Pending |

---

## 18. Document History

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-08-06 | Manual QA Engineer | Initial test plan |
| 1.1 | 2026-08-06 | Manual QA Engineer | Added dish details and customer reviews coverage |

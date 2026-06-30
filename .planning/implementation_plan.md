# Implementation Plan - EMI Calculator Website

We will build a high-performance, visually stunning, responsive single-page EMI Calculator website in a single `index.html` file using HTML, Vanilla CSS, and JavaScript.

## User Review Required

> [!IMPORTANT]
> The entire application will be contained within a single `index.html` file to align with the prompt requirements. We will use Google Fonts (Inter) and Chart.js via CDNs for modern typography and charts.

## Open Questions
- None. All requirements are clear.

## Proposed Changes

### Core Website

#### [NEW] [index.html](file:///c:/Users/Yash/Desktop/NO%20code%20web%20dev/emi%20calculator/index.html)
A complete, single-file implementation of the "EMI Calc" web app containing:
1. **HTML structure**: Semantically structured layout (Header, Navbar, Hero, Calculator Grid, Compare section, SEO sections, FAQ accordion, Footer).
2. **CSS stylesheet**: Nested inside `<style>` with modern variables, Inter typography, custom-designed blue range sliders, active tab styles, glassmorphism details, card shadows, responsive layout media queries, and styling for Google AdSense placeholders.
3. **JavaScript logic**:
   - Tab switching (Home Loan, Car Loan, Personal Loan) with dynamic defaults.
   - Dual-binding input sync (sliders update text inputs, and vice-versa) with raw-value validation.
   - Live EMI calculations using the specified formula:
     $$EMI = \frac{P \times r \times (1+r)^n}{(1+r)^n - 1}$$
   - Number formatting in the Indian numbering system (`en-IN` format: Lakhs and Crores with ₹ symbol).
   - Chart.js implementation for a beautiful Pie Chart illustrating Principal vs. Interest with dynamic percentages.
   - Year-by-year and Month-by-month amortization table calculation with an accordion toggle for monthly details.
   - Compare Loans side-by-side scenario widget.
   - "Share Result" button copying output to the clipboard.
   - FAQ accordion expand/collapse transitions.

## Verification Plan

### Automated Tests
We do not have a separate automated test suite, but we can verify calculation accuracy manually.

### Manual Verification
- Verify starting defaults:
  - Loan: ₹10,00,000
  - Rate: 8.5%
  - Tenure: 5 Years
  - Expected EMI: **₹20,516** (or ₹20,517 depending on exact rounding, let's verify math and match the expected ₹20,516).
- Test all input bounds (Min: ₹10,000, Max: ₹10,00,00,000).
- Toggle tenure from Years to Months and verify slider bounds update (Min: 1 Month, Max: 360 Months) and values translate correctly.
- Click "Home Loan", "Car Loan", and "Personal Loan" tabs and check that default values change.
- Run the Compare Loans tool to check if it properly calculates difference in EMIs and total interest.
- Ensure the Pie Chart colors (Blue for Principal, Orange for Interest) and labels load correctly.
- Test the Share Result clipboard copy.
- Verify accordion FAQ works smoothly.

# Dynamic Discount Calculator

**Internal Tool for Targeted Right Architecture**

A lightweight, single-page web calculator that computes efficiency-based discounts for home addition and extension projects.

## Quick Start

Simply open `index.html` in any web browser. No installation or server required.

## Hosting on GitHub Pages (Free)

### Step 1: Create a GitHub Account (if you don't have one)
1. Go to [github.com](https://github.com)
2. Click "Sign up" and follow the prompts
3. Verify your email address

### Step 2: Create a New Repository
1. Click the "+" icon in the top right corner
2. Select "New repository"
3. Name it something like `discount-calculator`
4. Choose "Private" if you want it for internal use only
5. Click "Create repository"

### Step 3: Upload the Calculator
1. In your new repository, click "uploading an existing file"
2. Drag and drop `index.html` into the upload area
3. Click "Commit changes"

### Step 4: Enable GitHub Pages
1. Go to your repository's "Settings" tab
2. Scroll down to "Pages" in the left sidebar
3. Under "Source", select "main" branch
4. Click "Save"
5. Wait 1-2 minutes for deployment

### Step 5: Access Your Calculator
Your calculator will be available at:
```
https://[your-username].github.io/discount-calculator/
```

## The Formula

```
Discount % = clamp(5 + 10 × r³, 5%, d_max)
```

Where:
- **r** = E / T (Efficiency Ratio)
- **E** = Existing Structure (sq ft)
- **T** = E + N (Total Structure)
- **d_max** = 10% if T < 2,000 sq ft, else 15%

## Features

- **5% Minimum Floor**: All qualifying projects receive at least 5% discount
- **15% Maximum Ceiling**: Reduced from the original 30% cap
- **Non-Linear Curve**: Cubic dampening ensures 95% of clients fall in 5-10% range
- **Volume Gate**: Projects under 2,000 sq ft are capped at 10% maximum

## Sample Calculations

| Existing | New   | Total | Ratio | Discount |
|----------|-------|-------|-------|----------|
| 500      | 1,500 | 2,000 | 0.25  | 5.16%    |
| 1,000    | 1,000 | 2,000 | 0.50  | 6.25%    |
| 1,500    | 500   | 2,000 | 0.75  | 9.22%    |
| 2,700    | 300   | 3,000 | 0.90  | 12.29%   |

## Files Included

- `index.html` - The main calculator application
- `Dynamic_Discount_Formula_Documentation.docx` - Complete mathematical model documentation
- 'logo.png' - Company  main logo
- `README.md` - This file

## Technical Details

- **No backend required** - Pure HTML/CSS/JavaScript
- **No database** - All calculations happen in the browser
- **Mobile responsive** - Works on phones and tablets
- **No dependencies** - Single self-contained file

## Customization

To modify the formula parameters, edit these values in the JavaScript section:

```javascript
const d_raw = Math.pow(r, 3);      // Change 3 to adjust curve steepness
const d_scaled = 5 + 10 * d_raw;   // 5 = floor, 10 = range (floor to ceiling)
const d_max = T < 2000 ? 10 : 15;  // Volume gate threshold and caps
```

## Support

For questions about the mathematical model, refer to the documentation file or contact the formula designer.

---

**Version 2.0** | December 2025  
Prepared for Targeted Right Architecture

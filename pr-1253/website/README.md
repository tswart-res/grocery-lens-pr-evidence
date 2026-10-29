# Actual website image usages — PR 1253

These are browser screenshots of the actual local Grocery Lens Django application: its real views, templates, styles and JavaScript, with six seeded listings covering all five retailers. Photos are actual retailer photos from the approved benchmark, encoded using the proposed implementation. Main/original/medium/large URL fields point to one WebP main asset; small points to the thumbnail. Browser image requests are fulfilled with those exact encoded bytes, avoiding production uploads. No application HTML, CSS or JavaScript responses are replaced. Displayed prices and non-image listing metadata are test values, not current retailer offers.

The isolated live-server browser test passed on 2026-10-29. It checked 44 image renderings for correct main/thumbnail URL, successful browser decoding, exact natural dimensions and a visible, nonzero display size, plus a hover zoom check (45 checks total). Zoom uses the same main URL as its background and responds to pointer movement. All screenshots were visually inspected. The original capture scripts and generated evidence remain in ignored local storage, outside the application repository's commit history.

| Usage | URL rendition | Evidence |
| --- | --- | --- |
| Search cards | main | desktop and mobile |
| Favourites | main | desktop |
| Product detail | main | desktop and mobile |
| Product hover zoom | main | desktop, pointer active |
| Comparison | main | desktop, both groups of three |
| Basket rows | thumbnail | desktop and mobile |
| Checkout cards | thumbnail | desktop |

Desktop viewport: 1440 × 1100. Mobile viewport: 390 × 844. Full-page mobile captures preserve the site's existing fixed bottom navigation. This verifies representative website usages with the new file contract; it is not a production deployment, a whole-catalogue visual audit, or a production CDN/performance check. The live production canary remains required before bulk cleanup. See verification-summary.json for product IDs and counts.

# PR 806 micronutrient UI evidence

Current captures in `2026-10-07/` come from four passing Chromium Playwright journeys
against a freshly created isolated PostgreSQL test database. They show the actual
Django templates and JavaScript after Premium gating and merging main. Accounts are
generated test accounts; no production sessions or customer data were used.

The product editor uses a saved high-iron per-100g profile. The recipe editor uses
a separate per-serving profile with Low minimum confidence. Free/downgraded accounts
show the lock; a staff account without a subscription sees the editor. The Premium
card uses the test fixture's plan/price and is evidence of feature copy, not a
statement of deployed production pricing.

The filtering screenshots use the audited iron regression controls and deliberate
unknown/stale/low-confidence fault controls. Product/recipe detail screenshots use
real CoFID cocoa estimates (with the USDA comparison loaded). These are functional
UI evidence, not measured accuracy or catalogue completeness certification.

`history/` preserves the 13 previous local preview screenshots that were removed
from the application PR's file diff. These are older revisions, not current paywall
screenshots. Fresh evidence is stored here so the private application repository
does not need new image assets.

Source test: `refiner/tests/playwright/diet/test_micronutrient_search_journey_e2e.py`.
Set `MICRONUTRIENT_SCREENSHOT_DIR` to a checkout of this repository's PR folder to
recapture. Existing files outside `806/` were not changed.

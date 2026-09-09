# PR 801: Sainsbury's sync and retailer registry

Visual evidence captured on 9 September 2026 from source commit `6c3e94f4e15ea5706969fe71728d72a8d0570282` (including the corresponding working-tree changes before commit).

## Capture provenance

- `faq-*`, `home-*`, and `privacy-*`: actual locally served Django pages, captured with Chromium. Desktop viewport 1440×1050; responsive FAQ viewport 390×844. Some images crop to the relevant page section.
- `checkout-*`: actual Django checkout templates with synthetic test database fixtures. Covers a supported Sainsbury's basket with a registered test device, an unsupported Tesco basket, and simulated extension-installed detection. No push notification or retailer mutation was sent.
- `sainsburys-*`: actual extension popup source with deterministic mocked browser messaging and basket data. Shows quantity differences and the explicit empty-target removal warning; no live sync was performed for these captures.

Screenshots were visually inspected for readable copy and layout. They document UI states, not proof of live API or payment execution. Live integration coverage and remaining manual checks are recorded in the private PR's test evidence document. No private retailer account details, session credentials, or customer records are included.

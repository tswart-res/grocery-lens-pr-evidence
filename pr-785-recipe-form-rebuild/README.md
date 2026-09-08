# PR #785 — Rebuild the create/edit recipe form

Captured in a real browser against the dev database (2,958 ingredients, 9,370 recipes).
"Before" is the pre-branch code at `c46b1ba6`, served from the same machine and data.

The first round of "after" shots used a two-column layout with a right-hand action rail.
That was rejected in review as wasted space, so those shots were replaced with the
single-column layout below.

| Shot | What it shows |
|---|---|
| `before-01-desktop-create.png` | The old form: Bootstrap-blue ingredients header against the site's green brand, red circular delete buttons, duplicated headings, no cuisine/image fields, no per-ingredient notes or purpose, instructions as one free-text blob. 8,937 `<option>` elements, 942.4 KB of HTML, 3 Select2 widgets. |
| `after-06-single-column-with-steps.png` | The rebuild: single column, full-width action bar at the end, section titles sitting cleanly inside their cards, cuisine and image exposed, and instructions entered as discrete numbered steps that round-trip on edit. |
| `after-02-combobox-open.png` | The in-repo combobox replacing Select2, live against real data — 14 matches for "carrot" with department paths and an announced count. Queries only at 3+ characters. |
| `after-03-new-ingredient-fields.png` | `purpose`, `notes` and `is_optional` — the fields the old page's help text promised but never offered. |
| `before-02-mobile-no-save.png` | Old mobile: the only submit button sat 2,173px below the fold with no persistent affordance. |
| `after-07-mobile-single-column.png` | New mobile: fixed action bar clear of the site's bottom tab bar, with every control verified clickable via `elementFromPoint` rather than bounding-box geometry. |
| `after-05-duplicate-ingredient-error.png` | D7 — adding the same ingredient twice previously returned a 500. It now names the ingredient and suggests a fix. |

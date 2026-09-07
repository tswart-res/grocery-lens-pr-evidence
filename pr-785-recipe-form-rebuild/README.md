# PR #785 — Rebuild the create/edit recipe form

Captured in a real browser against the dev database (2,958 ingredients, 9,370 recipes).
"Before" is the pre-branch code at `c46b1ba6` served from the same machine and data.

| Shot | What it shows |
|---|---|
| `before-01-desktop-create.png` | The old form: Bootstrap-blue ingredients header against the site's green brand, red circular delete buttons, duplicated "Basic Information" / "Recipe Details" headings, no cuisine or image fields, no per-ingredient notes or purpose. 8,937 `<option>` elements, 942.4 KB of HTML, 3 Select2 widgets. |
| `after-01-desktop-create.png` | The rebuild: two-column grid mirroring the recipe detail page, brand tokens throughout, cuisine and image exposed, per-ingredient "Preparation notes and purpose" disclosure, quantity help text rendered. 60 options, ~123 KB. |
| `after-02-combobox-open.png` | The in-repo combobox replacing Select2, live against real data — 14 matches for "carrot" with department paths and an announced result count. Queries only at 3+ characters. |
| `after-03-new-ingredient-fields.png` | `purpose`, `notes` and `is_optional` — the fields the old page's help text promised but never offered. |
| `before-02-mobile-no-save.png` | Old mobile: the only submit button sat 2,173px below the fold with no persistent affordance. |
| `after-04-mobile-save-reachable.png` | New mobile: fixed action bar, both Save and Cancel clickable and clear of the site's bottom tab bar. |
| `after-05-duplicate-ingredient-error.png` | D7 — adding the same ingredient twice previously returned a 500. It now names the ingredient and suggests a fix. |

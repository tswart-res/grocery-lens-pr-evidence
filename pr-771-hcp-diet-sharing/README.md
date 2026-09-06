# HCP referral invitation + diet sharing — screenshot walkthrough

Captured by `billing/tests/playwright/test_screenshot_walkthrough.py`. Full-page screenshots at 1440x900,
in flow order. Regenerate with:

```
HEADLESS=true uv run pytest billing/tests/playwright/test_screenshot_walkthrough.py -v
```

| Screenshot | What it shows |
|---|---|
| `01-hcp-dashboard.png` | The healthcare dashboard as a freshly verified professional sees it, with no referrals yet. |
| `02-create-referral-form.png` | The create-referral form filled in, showing the confirm-address field and the "email this link to the patient" checkbox. |
| `03-referral-created-success.png` | The success modal after creating the referral, confirming the invitation was emailed and showing the referral link. |
| `03a-invitation-email.png` | The invitation the patient receives, rendered from the sent message's own HTML exactly as their mail client shows it: the practitioner and institution, the accept link, and the referral discount. |
| `04-dashboard-with-referral.png` | The dashboard listing the new referral with its Edit and Resend invite controls, before the patient has an account. |
| `05-assign-diet-selected.png` | The assign-diet row after the patient has signed up (via the referral): a diet selected in the dropdown and "Allow this patient to customise" checked. |
| `06-dashboard-after-assign.png` | The dashboard after assigning, showing the live share ("Low FODMAP Protocol (customisable)") with its Revoke button. |
| `07-patient-diet-list-shared-badge.png` | The patient's diet list showing the assigned diet with its "Shared by Priya Chandrasekaran, Riverside Community Clinic" badge. |
| `08-patient-diet-list-no-edit-controls.png` | The same list state, confirming no edit control is offered on a shared diet (this list has only the one shared diet). |
| `09-patient-fork-of-shared-diet.png` | The diet builder after the patient opens the customisable shared diet: it forks into a private copy the patient owns, editable. |
| `10-fork-community-option-disabled.png` | The fork's Visibility control: the Community option is disabled, with the note "Shared with you by Priya Chandrasekaran, Riverside Community Clinic, so this diet stays private." The server still refuses the change if it is forced through. |
| `11-patient-diet-list-after-revoke.png` | The patient's diet list after the professional revokes the share: the shared original is gone. The "Low FODMAP Protocol" still listed here is the patient's own private fork from step 9, unaffected by the revoke -- not the revoked share. |

## Notes for reviewers

- The "Your Referral Link" panel on the dashboard renders as a bare `#` (visible in every dashboard
  screenshot). This is not an artifact of the test environment: `referral_url` is the hardcoded string
  `"#"` at `billing/views_freemium.py:345`, left behind when the shared HCP referral code was replaced by
  per-patient links. Every real professional sees the same dead panel and a Copy Link button that copies
  `#`. Pre-existing, out of scope for this branch, raised separately.

# Groww Reviews Analyser — Weekly Pulse

**Live prototype:** https://groww-review-analyser-final.vercel.app/

Turns 8–12 weeks of App Store + Play Store review exports into a one-page
weekly pulse: top themes, real user quotes, and three action ideas — then
drafts an email with that note.

## What's in this folder
| File | Purpose |
|---|---|
| `signal-weekly-pulse.html` | Local copy of the working prototype (same as the live link). Open in a browser. Upload a CSV or use the bundled sample data. |
| `reviews_sample.csv` | Sample/redacted review export used by the prototype (116 rows, 12 weeks, no PII). |
| `weekly-note-latest.md` | The generated one-page note for the most recent week in the sample data. |
| `email-draft.txt` | The draft email built from that note. |
| `README.md` | This file. |

## How to re-run for a new week

1. **Export reviews.** Pull your latest App Store / Play Store review export
   (public review data only — no scraping behind logins) as a CSV with these
   columns: `date, platform, rating, title, text`. Do not include usernames,
   emails, or reviewer IDs.
2. **Open the prototype.** Go to https://groww-review-analyser-final.vercel.app/
   (or open `signal-weekly-pulse.html` locally — same tool).
3. **Upload the CSV.** Use the upload control, or paste rows directly. The
   tool keeps the most recent 8–12 weeks and drops anything older.
4. **Review the themes.** The tool buckets each review into one of the five
   themes below (keyword match, editable in the code) and shows a 12-week
   trend per theme.
5. **Generate the note.** Click "Generate weekly note." This calls Claude to
   pick the top 3 themes, select 3 representative quotes, and write 3 action
   ideas, capped at 250 words, with no PII.
6. **Draft the email.** Click "Draft email" to turn the note into a
   ready-to-send email addressed to yourself/your team alias. Copy it into
   your mail client — this tool does not send email itself.
7. **Save the outputs.** Export the note (Markdown) and the email draft for
   your weekly record, same as the two files bundled here.

## Theme legend

| Theme | Covers |
|---|---|
| **Onboarding** | Signup, account creation, first-run tutorial, phone/email verification |
| **KYC** | Identity verification, document upload, selfie checks, approval delays |
| **Payments** | Sending/paying, UPI/card transactions, failed or pending payments |
| **Statements** | Transaction history, monthly statements, exports (PDF/CSV) |
| **Withdrawals** | Cashing out to bank, withdrawal limits, fees, payout delays |

Reviews that don't clearly match a theme are grouped as "Other" and excluded
from the weekly note (max 5 themes, per the brief).

## Constraints this tool follows
- Only public review exports are used — no scraping behind logins.
- Max 5 themes.
- The weekly note is capped at ≤250 words.
- No usernames, emails, or reviewer IDs appear in any output — quotes are
  review text only, and the sample CSV has no PII columns.

## Notes on the sample data
`reviews_sample.csv` is synthetic, generated to mirror realistic review
patterns for a fintech-style app (onboarding, KYC, payments, statements,
withdrawals) across 12 weeks. It is safe to share as-is.

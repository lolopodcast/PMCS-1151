# PMCS-1151 · Worksheets 學習單

Weekly worksheets for **PMCS (EMI)** — *Introduction to Project Management and Career Strategy as a Product Manager in the AI Era* — semester 1151, Prof. Shihmin Lo, Department of International Business Studies, National Chi Nan University.

**Live:** https://lolopodcast.github.io/PMCS-1151/

| Block | Weeks | Paths |
|---|---|---|
| The Architecture of Working with AI | W3–W5 | `/W03/` `/W04/` `/W05/` |
| The Product Manager: Role, Competency, Career | W6–W8 | `/W06/` `/W07/` `/W08/` |
| Building Your Morning-Brief Agent | W10–W12 | `/W10/` `/W11/` `/W12/` |
| Project Management: Planning, Controlling, Delivering | W13–W15 | `/W13/` `/W14/` `/W15/` |

Each worksheet is one self-contained HTML file (`index.html`) — React, Tailwind and DOMPurify are loaded from pinned CDN versions; there is no build step. Student answers are kept in the browser's `localStorage` and never leave the device; submission is by exporting Markdown or CSV and uploading to Moodle.

## Notes for maintenance

- The index page carries a **passphrase curtain**, not security. The passphrase is hard-coded in front-end JavaScript, so anyone who opens view-source or DevTools can read it. It keeps casual passers-by out of the entry page; it is not a guarantee that the contents stay private, and it must never be reused as a password for any real account. Deep links such as `/W03/` bypass it by design — the worksheets are course material, and this layer is a curtain in the same sense as the domain lock below.
- **The gate accepts a student number, not just the passphrase** (2026/08/25). It takes `proflolothebest` or anything matching `/^s?\d{9}$/` once whitespace and hyphens are stripped and the case is folded, so `s112212015`, `S112212015`, `112212015` and `s-112-2-12-0-15` all work — students will type all four. **The format is all that is checked, and there is no roster in this page; there must never be one.** A list of student numbers committed to a public, search-indexed repository is a disclosure that cannot be undone, and it would not stop anyone determined in any case. The gain is different: the class no longer shares one secret that ends up screenshotted into a group chat. The hub (`PMCS-1151-Hub`) runs the same rule, so a student uses their own number on both sites.
- **The gate never stores what was typed.** It used to write the passphrase itself into `localStorage`; under the new rule that would have written the student's own number onto their device. It now writes `pmcs1151_gate = '1'`, and the read still accepts the old value so anyone already through is not asked again. A test covers sixteen accept/reject inputs, asserts nothing but the flag is stored, and asserts the legacy value still unlocks.
- **The gate screen says nothing beyond the course name.** No placeholder, no example, no format, no note about where the number goes, and a rejection that reads only "that did not work". Students are told what they need in class and on Moodle, which authenticates them; this screen is read by whoever wanders in, and not stating the pattern is the only thing a curtain has going for it. (The regex is still in this file's source, as it must be — the change is about what the screen announces.)
- **The gate has its own theme and language buttons,** because the header ones sit behind it. The language button was always here; the theme button was added on 26 August, when it became clear that the reason for one applied identically to the other.
- **Light theme was measured, not assumed.** The gate background is `var(--ink)` (`#004030`) in light and `#02100B` in dark, so the lighter one is the harder case: `.gatesub` at 55% opacity measured 4.21 there and passed only in dark, which is why the first check missed it. It is now 78%, and both themes measure zero AA failures.

- Unlocking is remembered in that browser's `localStorage` under `pmcs1151_gate`. A different computer, a cleared cache or a private window will ask again.
- Every worksheet enforces a **domain lock**: it runs on `lolopodcast.github.io`, `localhost` and `127.0.0.1` only. Serving it from another host shows a notice instead of the content.
- Required-reading links point at the six teaching SPAs (AIWE, AGEN, IPOB, JDKS, PLAN, CTRL) and at the Hub. Those URLs are hard-coded, so the repositories behind them must keep their current names.
- The group CSV export carries a self-describing `Meta` block that configures the teacher's aggregator (`PMCS_Aggregator.html`). Changing a section-6 field id or a checkpoint wording means updating the aggregator's `WEEK_SPECS` too.

© Prof. Shihmin Lo. For educational use in this course.

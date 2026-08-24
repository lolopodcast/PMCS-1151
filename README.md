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
- Unlocking is remembered in that browser's `localStorage` under `pmcs1151_gate`. A different computer, a cleared cache or a private window will ask again.
- Every worksheet enforces a **domain lock**: it runs on `lolopodcast.github.io`, `localhost` and `127.0.0.1` only. Serving it from another host shows a notice instead of the content.
- Required-reading links point at the six teaching SPAs (AIWE, AGEN, IPOB, JDKS, PLAN, CTRL) and at the Hub. Those URLs are hard-coded, so the repositories behind them must keep their current names.
- The group CSV export carries a self-describing `Meta` block that configures the teacher's aggregator (`PMCS_Aggregator.html`). Changing a section-6 field id or a checkpoint wording means updating the aggregator's `WEEK_SPECS` too.

© Prof. Shihmin Lo. For educational use in this course.

# Swiss Ledger design language

Chosen by Roger on 26 Nov 2026 from three first-round drafts made by Gemini. First used on the VedicVA Jyotish timing report (repo vedicva, index.html, commit 6ea4c61).

## Principles
- Zero fluff, high signal. Every element carries data.
- Pure CSS and inline SVG. No external fonts, CDNs or libraries, so it works offline.
- Single file, mobile first, one centred ledger column.

## Tokens (light theme only)
| Role | Token | Value |
|---|---|---|
| Page ground | --bg-surface | #F7F7F5 |
| Column / cards | --bg-canvas | #FFFFFF |
| Alt surface | --bg-surface-alt | #EFEFEB |
| Hairline rule | --border-hairline | #E2E2DE |
| Strong rule | --border-strong | #111111 |
| Ink primary / secondary / muted | --ink-* | #111111 / #52524E / #767670 |
| Favourable | --st-fav / -bg | #146C43 / #F2F9F5 |
| Moderate | --st-mod / -bg | #1B5E8A / #F2F7FA |
| Mixed | --st-mix / -bg | #9A5B00 / #FCF8F0 |
| Calm / hold | --st-calm / -bg | #5A626A / #F5F6F7 |
| Caution | --st-caut / -bg | #B42318 / #FDF3F2 |

Geometry: radius 3px, header 56px, bottom nav 60px, column max width 720px.

## Typography
- Sans: system stack (-apple-system, Inter, Helvetica Neue, Arial). Mono: ui-monospace stack with tabular numbers for dates and figures.
- Base 15px, line height 1.48.
- Section titles 15px, weight 800, uppercase, under a 1.5px black rule.
- Micro labels 10.5px, weight 700, uppercase, letter-spacing 0.08em, muted ink.
- Card titles 14.5px weight 700; body copy 12.5 to 13px secondary ink.

## Layout
- App shell: fixed top header (brand name uppercase + mono year span + one-line subtitle), centred column with hairline side borders (dropped under 720px), fixed bottom nav.
- Bottom nav: 5 tabs, each a 19px line icon over a 10px uppercase label; active tab gets surface fill and a 2.5px black bar on top.
- Content padding 14px; stacks use gap 12px.

## Components
- Status badge: uppercase 10px, 1px border in status colour on its tinted ground.
- Status left border: 4px in status colour on cards and strips.
- Confidence tag: mono, uppercase, hairline box.
- Segmented control: 3 equal buttons in a black-bordered bar; active is inverted (black ground, white text).
- Filter pills: horizontal scroll with snap, no scrollbar; active pill inverted.
- Key-value ledger rows: hairline-separated list, bold key, secondary value.
- Window card: date + badges row, title, one-line verdict, area tags, then an accordion ("audit") of label/value rows on a 112px label grid, plus an optional refinement box with a 3px black left rule.
- Calendar matrix: year column + 12 month cells (30px, mono), status-coloured; selected cell gets a 2px black outline and drives an inspect panel below.
- Legend bar on surface ground with 10px swatches.
- Print stylesheet: hides nav and controls, opens accordions, keeps status colours.

## Touch and access
- Tap targets 36 to 54px high; buttons have aria-labels; main view is aria-live.

## Gaps to settle when reusing it
- No dark theme yet.
- The VA logo is not in this draft.
- Status colours are repeated as literals in the script (STATUS_COLORS); keep them in step with the tokens.

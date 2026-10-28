# Design

The calculator is a **quotation sheet**: every calculation reads like a supplier's ruled, numbered and stamped price quote (عرض سعر), on a sheet of paper lying on a grey-mauve desk. Arabic RTL first; English mirrors it with logical properties.

## Tokens (`:root` in `index.html`)

| Token | Value | Use |
|---|---|---|
| `--ink` | `#17131a` | text, heavy rules, selected segment |
| `--ink-2` | `#4b4250` | secondary text (descriptions, notes) |
| `--mute` | `#6c6270` | labels, sub-lines, line numbers |
| `--rule` | `#e4dee7` | hairline row rules |
| `--desk` | `#ebe7ed` | page ground around the sheet, tear-line notches |
| `--paper` | `#ffffff` | the sheet |
| `--stamp` / `--stamp-soft` | `#7a1460` / `#f7ecf3` | company ink: stamp, edited values, hover, focus ring |
| `--wa` / `--wa-dark` | `#0e7a5c` / `#0a5f47` | WhatsApp order button only |
| `--alert` / `--alert-soft` | `#b3261e` / `#fcecea` | rate outside the approved range, remove hover |

Type: **Readex Pro** (Google Fonts, 300–700), tabular figures everywhere. Three sizes: `--f-s` .8125rem (labels, notes), `--f-m` 1rem (body, table), `--f-l` 1.75rem (system name, area, grand total). Rank comes from weight and rules, not more sizes.

## Components

- **Letterhead**: logo, title (calculator title on the index, "عرض سعر مواد" on a calculation), subtitle, sales tag, language button; a 3px ink rule with a thin second rule under it.
- **Register (index)**: ruled two-column list under a 1.5px ink heading rule; each row is name + where it's used (the parenthetical split out) + arrow icon. Systems first, then single products.
- **Job details**: fill-in lines; inputs have only a 1.5px bottom rule; the colour choice is a two-cell ruled segment (selected = ink fill).
- **Bill of quantities**: line number (application order), material, rate (+ thickness sub-line), quantity, pack price, packs, cost; ink rules above and below the header, hairlines between rows. Removed lines are struck and hatched. On phones each line becomes a numbered item with the rate on its own row and label/value pairs in two columns.
- **Summary**: counts on the start side with the rubber stamp (plum, double border, rotated −7°, "تقدير مبدئي" + date); bill on the end side, grand total between a 1.5px rule and a double rule.
- **Notes**: numbered terms in two columns, small type, like the conditions under a quote.
- **Order slip**: a tear-off stub under a dashed perforation with notches cut into the sheet edge; city field, WhatsApp button, QR on desktop.
- **Sticky bar (phones)**: total + order button under a 1.5px ink rule.

Corners are 3px everywhere (paper and stamped boxes, not pills). Icons are inline stroke SVGs (arrow, reset); no glyph icons.

## Motion

One authored moment: when a total changes, only the digits that differ roll in (`roll()` + `.roll`, 450ms expo-out with a slight blur). Disabled under `prefers-reduced-motion`.

## Breakpoints

- ≥1180px: job details (250px, sticky) beside the bill of quantities.
- 701–1179px: job details as a row of fields above the table.
- ≤700px: sheet goes edge to edge, table becomes line items, sticky order bar.

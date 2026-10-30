# Watch Box

The owner is new to coding. Explain things in plain language and give click-by-click steps for anything they must do themselves.

## App (plain HTML/CSS/JS, no build step)
- `index.html`: **Watch Box** ("PYB’s Watch Box"), a self-contained single file that tracks the owner's watches and their value.
- Data lives in browser localStorage, key `watchBox.v1`: `{watches:[{id, brand, model, ref, year, cond, set, paid, bought, value, cur, notes, photo, history:[{d, v}]}]}`. `photo` is a 600px JPEG data URL (shrunk in the browser). `history` gets one entry per day when the value changes.
- Values are typed in by hand. Each watch links to a Chrono24 search for its reference number. Chrono24 has no public API, so nothing is fetched from it.
- Totals use the most common currency; watches in other currencies are counted separately.
- JSON backup/restore, plus CSV export/import (column names matched loosely via `ALIAS`).
- Don't break existing saved data: keep the localStorage key and backup format compatible.

## Publishing
- GitHub Pages: https://poochyb.github.io/Watches/
- Pages serves the branch `claude/bold-darwin-3dk2ya`. Changes only go live once they are on that branch.

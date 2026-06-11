# Ezra's Tools

Single-file vanilla HTML/CSS/JS web tools, deployed via GitHub Pages at
https://projectezrabart.github.io/tools/. No build system — each tool is a
self-contained .html file linked from index.html.

## morning-checklist.html

- **On every change to this file, bump `APP_VERSION` and set `APP_UPDATED`**
  (NZ local date/time) near the top of the `<script>` block. These render in
  the small footer under the add-task bar.
- The "routine day" rolls over at **noon local time**, not midnight — tasks
  ticked the night before count toward the next morning. Keep this in mind
  for any date logic (`todayStr()` subtracts 12 hours).
- localStorage keys: `morning_tasks_v3` (task list + order) and
  `morning_state_v3` (per-day completion). Bump the key suffix if the stored
  data shape changes.
- Touch interactions are delicate and have broken before: tap-to-toggle,
  long-press-to-edit, grip drag-to-reorder, and swipe-left-to-delete all
  share document-level touchmove/touchend handlers. Test all four after
  touching any of that code.

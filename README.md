# Upper School schedule

A single-file schedule builder for 6th, 7th, and 8th grade. Open `index.html` in any
browser — no build step, no dependencies, no network access required.

## How it works

Pick your grade first. The controls below it reconfigure to match:

| Grade | First choice | Second choice |
|-------|--------------|---------------|
| 6th | 1-block (6B1 / 6P1 / 6C1) | 2-block (6B2 / 6P2 / 6C2) |
| 7th | 1-block (7B1 / 7P1 / 7C1) | Language block (7BL / 7PL / 7CL) |
| 8th | 1-block (8B1 / 8P1 / 8C1) | 2-block (8B2 / 8P2 / 8C2) |

The two choices are independent — a student can be 7B1 + 7CL, or 8C1 + 8B2. The blocks
never overlap in the same period, so every combination produces a conflict-free week.

Optionally set an advisor (fills in period 1) and a student name (prints on the output).

## Print layouts

**All 5 days on one page** — letter landscape. Days run in columns positioned by real
clock time on a shared 8:20–3:10 axis, so the M/W/F and Tu/Th bell differences are
visible. Break and lunch appear as the actual gaps between blocks.

**5 cards, one day each** — letter portrait, one 3.5 × 2.75 in card per page with a
black cut line to trim on. Set print scale to 100%, not "fit to page," or the cut size
will be wrong.

## Schedule notes

- Period 1 is advisory on M/W/F only; Tu/Th period 1 is a class.
- Friday period 2 is an all-school assembly (ASG/USG) for every grade.
- Office hours meet twice a week with different cohorts. For 6th and 8th: Tuesday with
  your 1-block, Thursday with your 2-block. For 7th: Tuesday with your language block,
  Thursday with your 1-block.
- Bell times differ by day type. M/W/F break is 10:36–10:54 and lunch 12:40–1:24;
  Tu/Th break is 10:03–10:21 and lunch 12:07–12:47.
- Back-to-back doubles (science, art) are intentional, not data entry errors.

## Editing

Everything lives in `index.html`. The two things you're most likely to change:

- `NAMES` — maps teacher initials to display names.
- `SCHED` — the schedule itself, keyed `SCHED[grade][day][period]`. Each entry is
  `[blockType, {B: [...], P: [...], C: [...]}]` where `blockType` is `"1"`, `"2"`,
  `"L"`, or `"x"` (all-grade, e.g. assembly), and each split maps to
  `[class, teacherInitials, room]`.

Source: the Upper School master schedule spreadsheet.

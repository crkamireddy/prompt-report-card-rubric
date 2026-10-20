---
description: Re-grade the calibration set and report where the grader has drifted
argument-hint: (no arguments)
allowed-tools: Read, Bash, Write
---

Check whether the grader still agrees with the settled grades in `examples/`. Drift here
means the same prompt would get a different letter than it did before — usually after an
edit to `RUBRIC.md`, sometimes after a model change.

Order matters. Do not read `examples/expected.json` until step 3.

1. Read `RUBRIC.md`. List `examples/*.md`.

2. Grade each example against the rubric. Full internal pass per prompt — score every
   dimension, reach a letter — but do not write the reviews out. Record only the letter
   and the anti-patterns you cited. Grade every example before moving on; do not check
   any answer partway through.

3. Now read `examples/expected.json` and compare.

4. Report:

   A table: file, expected grade, your grade, and `ok` or `DRIFT`. A grade inside that
   example's `accept` list is `ok`.

   For each `DRIFT` row, one paragraph — which dimension moved and why you scored it
   differently than the recorded `why` says it was scored. Name the rubric section
   responsible. This is the useful part; the table alone says nothing actionable.

   A closing line on anti-patterns: any you cited that the record doesn't list, or that
   the record lists and you missed. New anti-patterns appearing across several examples
   usually means a catalog entry is too broad.

5. Say plainly whether this looks like grader drift or a deliberate consequence of a
   rubric edit, and stop. Do not edit `RUBRIC.md` or `expected.json` — if a new grade is
   the correct one, that is a decision for the author, and updating the record without
   being asked destroys the baseline the test exists to protect.

Nothing here is logged to `history/`. Calibration runs are not grades.

---
description: Weekly review with week-on-week comparison
argument-hint: [optional: this_week or last_week, default last_week]
---

Prepare a weekly review for $ARGUMENTS (default: last_week).

1. Call `aggregate_jobs` for the week with `compare_to` `previous_period`, for these metrics: `job_count`, `completion_rate`, `first_visit_fix_rate`, `avg_end_delta_mins`. Use time axis `actualEndAt` for completions and say which axis you used.
2. Call `aggregate_jobs` again for `job_count` and `completion_rate` grouped by `resourceId` (engineer) to find the strongest and weakest.
3. If the week is still in progress, say the figures cover the days so far.
4. Reply headline first, leading with the deltas against the previous week (for example "Completions are up 12%, 218 against 195"). Add a short table by engineer, then one or two points worth investigating, and offer `investigate` on the biggest mover.

Follow the field-service skill for units and data-quality rules (flag overruns above about 480 minutes as likely artefacts). Do not show internal IDs.

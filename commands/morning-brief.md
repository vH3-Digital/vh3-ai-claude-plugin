---
description: Start-of-day brief for today, plus early-warning sentinel checks
---

Prepare my morning brief.

1. Call `reports_generate` with `report_type` `start_of_day` and today's date (YYYY-MM-DD). Omit `sections`.
2. Call `run_sentinels` with no ids, to run every configured sentinel.
3. Reply in plain British English, headline first:
   - One sentence on how the day looks.
   - Today's workload and anything the report highlights or flags as a concern.
   - The sentinel findings, most urgent first, each with the job reference, engineer or site involved.
   - One suggested next step.

Follow the field-service skill for units, defaults and presentation. Do not show internal IDs. If either call fails, say so and carry on with the other.

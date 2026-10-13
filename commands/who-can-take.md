---
description: Who could take a job, and when, from live BigChange slots
argument-hint: <job reference> [earliest | efficient | suitable] [window]
---

Find who could take the job in $ARGUMENTS.

1. Read the job first: use `search_autocomplete` if you only have a reference, then `get_job`, to confirm the job and its site.
2. Call `scheduling_suggestions` with the job's `jobId`, no coordinates, a window of at most seven days starting now, and `prefer` from the request (`earliest` if unstated, `suitable` for "who is best"). If the user named people or groups, filter to them; otherwise state how the search was narrowed.
3. Report as the field-service skill says: the ranking criterion ("ranked by VH3 on ..."), the cap, who, local and UTC start, extra driving, deadline handling, late options only as late options, and the compliance caveat if performance figures are shown.
4. Remind the user that slots are BigChange's offers, not a leave check, and that a person applies a slot on the schedule. Do not book anything.

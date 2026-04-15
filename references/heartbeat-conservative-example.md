# Conservative Daily Work Review Heartbeat

tasks:

- name: weekday-work-review-nudge-conservative
  interval: 30m
  prompt: "Only consider sending a reminder if it is a weekday, local time is after 18:30, and the user appears to have been active in OpenClaw today or very recently. If today's work review has not happened yet, send one short reminder to start `$company-growth-check-in`. If the user was not active today, or already started or finished today's review, do not remind."

- Keep this check lightweight.
- Do not guess that the user is available if there is no sign of recent activity.
- If there is an urgent user-facing issue, surface that first.
- If no reminder is needed, reply with `HEARTBEAT_OK`.
- Keep reminders short and natural.

Example reminder:

Start `$company-growth-check-in` now. What is the single most important thing that happened at work today?

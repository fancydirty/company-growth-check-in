# Work Review Heartbeat

tasks:

- name: weekday-work-review-nudge
  interval: 30m
  prompt: "If it is a weekday, local time is after 18:30, and today's work review has not happened yet, send one short reminder to start `$company-growth-check-in`. If the user already started or finished today's review, do not remind again."

# Additional instructions

- Keep this check lightweight.
- If there is an urgent user-facing issue, surface that first.
- If no reminder is needed, reply with `HEARTBEAT_OK`.
- Keep reminders short and natural.

Example reminder:

Start `$company-growth-check-in` now. What is the single most important thing that happened at work today?

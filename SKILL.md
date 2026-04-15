---
name: company-growth-check-in
description: Use when the user explicitly invokes $company-growth-check-in to evaluate whether their current company or role is still worth staying in, whether they are still learning and growing, and how to turn daily work experience into better career decisions over time.
---

# Company Growth Check-In

## Overview

Use this skill to help a user evaluate a company or role with clear evidence instead of momentum, anxiety, or vague hope.

This skill is for ongoing career judgment, not journaling for its own sake. All discussion, notes, daily reports, and weekly or monthly reviews exist to answer two questions:

- Is this company or role still worth staying in?
- Is the user still getting meaningful growth from staying?

## When To Use

The simplest rule is:

- If the user explicitly says `$company-growth-check-in`, use this skill.

Common use cases:

- A daily or weekly check-in on whether the current company is still worth staying in
- A review of whether the user is still learning enough from the role
- A structured discussion about a confusing event with leadership, product, customers, or team dynamics
- A weekly or monthly review based on saved daily reports
- A first-time setup for a new company, role, or team

Example prompts:

- "Use $company-growth-check-in."
- "Use $company-growth-check-in. I want to review what happened today."
- "Use $company-growth-check-in and review this week from the saved reports."
- "Use $company-growth-check-in to set up context for my new role."

## Operating Modes

This skill supports three modes:

- **Bootstrap mode**: gather or refresh company and role context
- **Discussion mode**: agent-led daily or ad hoc check-in
- **Review mode**: weekly or monthly synthesis from saved reports

## Bootstrap Mode

Use bootstrap mode when:

- the skill is being used for the first time
- the company changed
- the role changed
- the saved context is missing or clearly stale

The goal is to create a useful factual base before offering judgment.

### Bootstrap Workflow

1. Ask for the minimum core identifiers:
   - company name
   - role title
2. If the company is public enough, research basic public facts.
3. Ask the user to confirm, correct, or fill gaps.
4. Save the current context to `context/current-engagement.md`.

If the company is very early, private, or not publicly legible, rely on the user's facts and mark unknowns clearly.

If research is weak, do not continue with a full discussion until you have at least this minimum fallback context:

- company name
- role title
- what the company does
- what the user most wants from the role
- what would make the role clearly worth staying in
- what would make the user start considering an exit

Use the template in [references/bootstrap-template.md](references/bootstrap-template.md).

## Discussion Mode

This skill should feel like a structured conversation, not a lecture.

Default interaction style:

- agent asks first
- ask one focused question at a time
- wait for the user's reply before continuing
- use the reply to refine the picture
- keep replies short during the live discussion
- do not give a full verdict too early

### Opening Move

If the user invokes `$company-growth-check-in` without enough detail, start with one question instead of starting with analysis.

Preferred opening question:

- "What is the single most important thing that happened at work in the last two days?"

Alternative opening questions:

- "What happened today that made you want to check in on this role?"
- "What is the one event this week that best reveals the company's real condition?"
- "The last time you talked to leadership, what did they say, and what actually changed afterward?"

Do not open with a verdict.
Do not open with a framework dump.
Do not ask multiple broad questions at once.

### Discussion Workflow

1. Summarize the user's facts in plain language.
2. Separate:
   - what was promised
   - what actually happened
   - what remains unknown
3. Ask the next most useful question.
4. Judge the situation on two axes:
   - **Company or role reality**: is there evidence of useful progress, clarity, and viability?
   - **User growth return**: is the user still getting enough learning, exposure, and career value from staying?
5. When enough evidence exists, give a narrow recommendation.

Question order should usually be:

1. What happened?
2. What was promised?
3. What actually changed afterward?
4. What did this reveal about the company, the role, or the user's growth?

Use the framework in [references/assessment-framework.md](references/assessment-framework.md) when a deeper pass is needed.

## Review Mode

If the user asks for a weekly or monthly review:

1. Read `context/current-engagement.md` first if it exists.
2. Read the relevant files under `reports/`.
3. Identify recurring patterns across:
   - operational reality
   - product or business movement
   - leadership quality
   - learning density
   - career optionality
4. Summarize what changed over time.
5. State whether the situation is becoming more useful, less useful, or simply clearer.
6. Write the result to:
   - `reports/weekly-review-YYYY-MM-DD.md`
   - `reports/monthly-review-YYYY-MM.md`

Use the template in [references/review-template.md](references/review-template.md).

## Recommendation States

Choose one clear recommendation:

- **Continue and invest**
- **Continue, but monitor**
- **Stay while building options**
- **Prepare exit**

Do not hedge unless the facts are truly mixed. If uncertainty remains, state exactly what needs to be verified next.

## Output Format

### During the live discussion

Keep replies short and question-led.

Use this pattern:

- brief read of the current signal
- one concrete takeaway if obvious
- one next question

Example shape:

- "Right now this looks mixed: the story is coherent, but I still cannot tell whether execution is real."
- "The useful part for you is that you are seeing how leadership frames the business."
- "Next question: after that conversation, what did they actually push forward?"

### When giving a summary or verdict

Use this structure:

### Verdict

One or two sentences on whether the company or role is still worth staying in.

### Evidence

List the strongest signals driving the verdict.

### Growth Return

State what the user is still getting:

- compensation or stability
- product exposure
- business exposure
- leadership observation
- skill growth
- career signal

### Key Lessons

State the most valuable lessons hidden inside the recent events.

### Next Move

Give the smallest next action:

- what to observe
- what to document
- what to ask
- what would trigger a stronger recommendation

## Daily Report Writing

At the end of each completed discussion, write a report into the skill directory.

Default location:

- `reports/YYYY-MM-DD.md`

Report rules:

- If the file for that date does not exist, create it.
- If the file already exists, append a new session entry instead of overwriting.
- Do not write the report in the middle of an active interview.
- If the environment cannot write files, output the report in chat and say that file writing was unavailable.

Use the template in [references/daily-report-template.md](references/daily-report-template.md).

## Report Writing Rules

The report is part of the workflow, not an optional extra.

Write the report only when the conversation reaches a clear stopping point. A clear stopping point usually means one of these:

- the user explicitly says "end", "summary", "write the report", or an equivalent closing instruction
- the user asks for a summary
- the user says the discussion is done for now
- enough facts exist for a recommendation and next move

If the user is still answering questions or the investigation is obviously ongoing, do not write the report yet.

## Guardrails

- Do not moralize.
- Do not assume the company is good or bad by default.
- Do not confuse confidence, polished communication, or internal messaging with evidence.
- Do not force the user to leave just because the company is messy.
- Do not tell the user to stay just because the mission sounds strong.
- Keep the focus on evidence, growth return, and decision quality.
- Treat this as an ongoing career decision aid, not a loyalty test.

## References

- For deeper assessment logic, read [references/assessment-framework.md](references/assessment-framework.md).
- For first-time setup and context capture, read [references/bootstrap-template.md](references/bootstrap-template.md).
- For the daily report format, read [references/daily-report-template.md](references/daily-report-template.md).
- For weekly and monthly synthesis, read [references/review-template.md](references/review-template.md).

---
name: startup-reality-check
description: Use when the user explicitly invokes $startup-reality-check to discuss whether a startup job or early-stage company is still worth staying in, what signals matter today, what can still be learned from it, and whether it is time to keep extracting value or prepare exit.
---

# Startup Reality Check

## Overview

Use this skill to help a user treat a startup job as a training ground instead of a belief system.

The goal is not to decide whether the company is "good." The goal is to judge, from concrete daily facts, whether the company is still worth exploiting for cash flow, product exposure, sales exposure, and execution experience.

All discussion, note-taking, daily reports, and weekly or monthly reviews exist for one reason:

- to decide whether this company is still worth staying in
- to decide whether the user is still getting meaningful growth from staying

Do not let the workflow drift into journaling for its own sake. The workflow exists to support better stay-or-leave judgment and clearer growth assessment over time.

## When To Use

The simplest rule is:

- If the user explicitly says `$startup-reality-check`, use this skill.

You can also use it when the user's request is obviously the same task, even without the exact skill name.

Typical use cases:

- A daily or weekly reality check on whether the startup is still worth staying in
- A weekly or monthly review based on accumulated daily reports
- A judgment about whether new company behavior is a red flag or just normal early-stage chaos
- Help extracting product, execution, sales, or founder lessons from today's events
- A stay-or-leave recommendation based on recent observations
- A way to convert messy work experiences into career signal and future founder knowledge

Example prompts:

- "Based on what happened today, is this company still worth staying in?"
- "I talked to the CEO and CPO again. What are the real signals here?"
- "Turn today's startup mess into lessons I can use later when I build my own product."
- "Give me a weekly checkpoint on whether I am learning enough to justify staying."

## Required Input

This skill defaults to an interviewer mode.

If the user invokes `$startup-reality-check` without giving enough detail, the agent should begin by asking the first question instead of starting with analysis.

If the user already gave facts, use those facts and then ask the next question.

If the user asks for a weekly or monthly review, read the relevant report files from `reports/` first, then synthesize instead of starting a fresh interview.

Useful inputs include:

- What happened today or this week
- What leaders said and what they actually did
- Product progress, user feedback, customer conversations, or launch movement
- Hiring, budget, equipment, tooling, payroll, or other cash signals
- What the user worked on and what they learned
- Any new friction: HR, devices, contracts, KPI, politics, chaos, or broken promises

Do not anchor on a single emotional event unless it changes the underlying situation.

If the user already gave enough detail, do not ask extra setup questions. Move straight into analysis.

## Workflow

This skill should feel like a structured discussion, not a lecture.

There are two modes:

- **Discussion mode**: used for a fresh daily check-in
- **Review mode**: used for weekly or monthly synthesis from saved reports

Default interaction style:

- Agent asks first
- Ask one focused question at a time
- Wait for the user's reply before continuing
- Use the reply to update the picture
- Do not dump the full framework immediately
- Only give a full verdict when enough evidence exists or when the user asks for a summary

### Opening Move

When the user explicitly invokes `$startup-reality-check`, start with a question unless they already provided a detailed situation summary.

Preferred opening question:

- "What is the single most important thing that happened at work in the last two days?"

Alternative opening questions when needed:

- "What happened today that made you question whether this startup is still worth staying in?"
- "What is the one event this week that best reveals the company's real condition?"
- "The last time you talked to leadership, what did they say, and what did they actually do afterward?"

Do not open with a verdict.
Do not open with a framework dump.
Do not ask multiple broad questions at once.

### Review Mode

If the user asks for a weekly or monthly review:

1. Read the relevant files under `reports/`
2. Identify recurring patterns across money, product, leadership, learning density, and exit risk
3. Summarize what changed over time
4. State whether the startup is becoming more useful, less useful, or simply clearer
5. Write the result to:
   - `reports/weekly-review-YYYY-MM-DD.md`
   - `reports/monthly-review-YYYY-MM.md`

Use the template in [references/review-template.md](references/review-template.md).

### 1. Build the factual timeline through questions

Start by summarizing what the user already said into plain facts. Then ask the next most useful question.

Separate:

- what was promised
- what actually happened
- what remains unknown

If the user mixes inference and fact, label the inference clearly.

Good question types:

- "What exactly happened?"
- "What did they say they would do next?"
- "What changed after that?"
- "Did any of this affect product, money, or your learning?"

Avoid asking many questions at once unless the user explicitly wants a full dump.

Question order should usually be:

1. What happened?
2. What was promised?
3. What actually changed afterward?
4. What did this reveal about money, product, leadership, or your learning value?

### 2. Judge the company on two axes

Always evaluate both:

- **Company viability**: Is there evidence this startup can turn story into product and product into money?
- **User value extraction**: Even if the company is weak, is the user still getting enough cash, product exposure, business exposure, or founder education to justify staying for now?

### 3. Score the signal quality

Use the framework in [references/assessment-framework.md](references/assessment-framework.md) when the user needs a deeper pass.

At minimum, judge these categories:

- money and operational reality
- product clarity and movement
- sales or monetization logic
- leadership quality and follow-through
- learning density for the user
- exit risk and replaceability

### 4. Convert events into founder lessons

Do not stop at "red flag" or "looks fine." Extract what the user can learn from the event about:

- product definition
- user demand
- pricing
- go-to-market
- team execution
- founder behavior

The user wants to eventually build and sell their own product. Keep orienting the analysis toward that end.

### 5. Give a narrow recommendation

Choose one clear recommendation:

- **Stay and keep extracting**
- **Stay, but watch closely**
- **Prepare exit while staying**
- **Exit soon**

Do not hedge unless facts are truly mixed. If uncertain, say what needs to be verified next.

### 6. Write a dated report at the end

At the end of each completed discussion, write a report into the skill directory.

Default location:

- `reports/YYYY-MM-DD.md`

Report rule:

- If the file for that date does not exist, create it.
- If the file already exists, append a new session entry instead of overwriting.
- If the environment cannot write files, output the report in chat and state that file writing was unavailable.
- Do not write the report in the middle of an active interview.

The report should preserve:

- what the user described
- what the user believed or worried about
- what the agent observed
- where the user's and agent's views matched or differed
- the current recommendation
- the next things to watch

Use the template in [references/daily-report-template.md](references/daily-report-template.md).

## Output Format

During discussion mode, keep replies short and question-led.

Use this pattern:

### During the discussion

- brief read of the current signal
- one concrete takeaway if obvious
- one next question

Example shape:

- "Right now this looks like a mixed signal: the story sounds coherent, but I still cannot tell whether execution is real."
- "The useful thing for you here is that you are watching leadership frame the business up close."
- "Next question: after that conversation, what did they actually push forward, even if it was small?"

### When giving a summary or verdict

Keep the output short, concrete, and non-therapeutic.

Use this structure:

### Verdict

One or two sentences on whether the startup is still worth staying in.

### Evidence

List the strongest signals driving the verdict.

### What You Are Still Getting

State what the user is still extracting:

- cash flow
- product reps
- business exposure
- founder education
- network or market understanding

### Founder Lessons

State the most valuable lessons hidden inside the recent events.

### Next Move

Give the smallest next action:

- what to observe
- what to document
- what to ask
- what would trigger exit preparation

## Report Writing Rules

The report is part of the workflow, not an optional extra.

When the conversation reaches a clear stopping point, the agent should write the report before ending.

A clear stopping point usually means one of these:

- the user explicitly says "end", "summary", "write the report", or an equivalent closing instruction
- the user asks for a summary
- the user says the discussion is done for now
- enough facts exist for a recommendation and next move

If the user is still answering questions or the investigation is obviously ongoing, do not write the report yet.

Keep the report factual and compact. It should be useful for future review, not ornamental.

For weekly or monthly synthesis, the review file should:

- summarize the strongest repeating signals
- summarize the most serious repeated risks
- capture what the user is actually gaining from the job over time
- state whether the current trend supports staying or preparing exit
- make it easy to compare one period to the next

## Summary Trigger

Do not force a final conclusion too early.

Give the full verdict when one of these is true:

- the user explicitly asks for a verdict, summary, or recommendation
- enough facts exist to make a grounded call
- the conversation has already surfaced the key signals across money, product, leadership, and learning value

## Guardrails

- Do not moralize.
- Do not tell the user to trust the company.
- Do not confuse charisma, founder talk, or HR smoothing with evidence.
- Do not advise immediate exit just because the company is messy; early startups are often messy.
- Do not advise staying just because the story sounds smart; look for product movement and money logic.
- Prioritize reality over ideology.
- Treat the company as a temporary platform the user is extracting value from, not as an identity.

## Reference

For deeper daily or weekly assessments, red flags, learning extraction prompts, and a simple scorecard, read [references/assessment-framework.md](references/assessment-framework.md).

For the report format, read [references/daily-report-template.md](references/daily-report-template.md).

For weekly and monthly synthesis, read [references/review-template.md](references/review-template.md).

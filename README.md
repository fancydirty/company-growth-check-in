# Company Growth Check-In

Turn daily work experience into clearer stay-or-leave career decisions.

`company-growth-check-in` is a reusable AI skill for one ongoing question:

**Is this company or role still worth staying in, and am I still getting meaningful growth from staying?**

It is designed for people who want better career judgment over time, not just a one-off reaction to a bad day.

## What It Does

The skill supports three modes:

- **Bootstrap mode**: gather context about the company, the role, and the user's goals
- **Discussion mode**: run an agent-led check-in where the agent asks focused questions one at a time
- **Review mode**: synthesize saved daily reports into weekly or monthly reviews

The output is meant to help with decision quality, not loyalty, morale, or generic journaling.

## Suggested GitHub Metadata

**Repository name**

- `company-growth-check-in`

**Description**

- `A reusable AI skill for deciding whether your current company or role is still worth staying in.`

**Topics**

- `career`
- `career-growth`
- `career-decisions`
- `agent`
- `ai-skill`
- `reflection`
- `check-in`
- `work-journal`
- `decision-making`
- `job-evaluation`
- `role-fit`
- `company-fit`

## Core Question

The skill keeps returning to two questions:

- Is this company or role still worth staying in?
- Is the user still getting meaningful growth from staying?

## Repository Structure

```text
company-growth-check-in/
|-- SKILL.md
|-- README.md
|-- RELEASE_NOTES.md
|-- .gitignore
|-- agents/
|   `-- openai.yaml
|-- context/
|   `-- .gitkeep
|-- reports/
|   `-- .gitkeep
`-- references/
    |-- assessment-framework.md
    |-- bootstrap-template.md
    |-- daily-report-template.md
    `-- review-template.md
```

## Install

### Codex

Copy this repository into your Codex skills directory as:

```text
~/.codex/skills/company-growth-check-in
```

On Windows, that is usually:

```text
C:\Users\<your-user>\.codex\skills\company-growth-check-in
```

After installing the folder, restart Codex so it picks up the new skill.

If your Codex environment has the built-in skill installer, you can also ask:

```text
Use $skill-installer to install https://github.com/fancydirty/company-growth-check-in
```

### OpenClaw

OpenClaw can load skills from multiple locations. The simplest workspace-local install is:

```text
~/.openclaw/workspace/skills/company-growth-check-in
```

If your OpenClaw workspace is customized, use:

```text
<workspace>/skills/company-growth-check-in
```

If you want the skill to be shared across agents on the same machine, use:

```text
~/.openclaw/skills/company-growth-check-in
```

After adding the folder, start a new OpenClaw session so the skill is picked up.

### Hermes Agent

Hermes Agent uses a single source-of-truth skills directory:

```text
~/.hermes/skills/company-growth-check-in
```

After adding the folder, start a new Hermes session. If you need the skill immediately in the current session, reset the session first.

## Proactive Reminders

If your agent platform supports scheduled or proactive turns, you can use this skill without having to remember the check-in manually every day.

### OpenClaw

OpenClaw supports both heartbeat and cron, but they are best used differently:

- use **heartbeat** for periodic awareness and gentle nudges
- use **cron** for an exact daily check-in time

If you want a daily reminder at a specific local time, prefer cron.

Example idea:

```text
At 18:30 every weekday, remind me to run $company-growth-check-in and start the check-in by asking the first question.
```

If you want a softer setup, use heartbeat plus a small `HEARTBEAT.md` rule such as:

```text
If it is after 18:30 local time on a weekday and today's work review has not happened yet, nudge me to start $company-growth-check-in.
```

### Hermes Agent

Hermes Agent uses scheduled cron jobs for this kind of proactive workflow.

Example idea:

```text
Every weekday at 18:30, ask me to start $company-growth-check-in and guide me through a short review of today's work.
```

### Suggested Agent Behavior

If the agent knows it is running in a platform with scheduling support, it should ask once:

- whether the user wants a recurring reminder
- whether the reminder should happen every day or weekdays only
- what local time the reminder should fire

For exact timing, prefer cron-style scheduling.
For soft periodic nudges in OpenClaw, heartbeat is also a good fit.

## How It Works

### 1. Bootstrap

On first use, or when the company or role changes, the agent gathers the minimum context needed to make later check-ins useful.

It saves that context to:

- `context/current-engagement.md`

For public or legible companies, the agent can research basic facts first and then ask the user to confirm or correct them.

For very early or private companies, the agent should rely on the user's facts and make unknowns explicit.

### 2. Daily Check-In

In discussion mode, the agent asks questions first. It does not start with a lecture or a verdict.

Typical flow:

1. Ask what happened
2. Clarify what was promised
3. Clarify what actually changed
4. Judge the signal
5. Write a dated report when the discussion ends

Daily reports are written to:

- `reports/YYYY-MM-DD.md`

### 3. Weekly Or Monthly Review

In review mode, the agent reads saved reports and synthesizes recurring patterns into:

- `reports/weekly-review-YYYY-MM-DD.md`
- `reports/monthly-review-YYYY-MM.md`

## Example Prompts

Bootstrap:

```text
Use $company-growth-check-in to set up context for my new role.
```

Daily check-in:

```text
Use $company-growth-check-in.
```

Weekly review:

```text
Use $company-growth-check-in and review this week from the saved reports.
```

End the discussion and write a report:

```text
Use $company-growth-check-in. Summary.
```

## Runtime Files And Privacy

This repository includes `context/` and `reports/` directories, but the generated Markdown files inside them are ignored by git.

Why:

- company and role details are often private
- daily reports may contain sensitive work details
- weekly and monthly reviews are usually personal working notes

The repository keeps only:

- `context/.gitkeep`
- `reports/.gitkeep`

The ignored runtime files are controlled by [.gitignore](./.gitignore).

## Recommendation States

The skill uses four recommendation states:

- `Continue and invest`
- `Continue, but monitor`
- `Stay while building options`
- `Prepare exit`

These states are meant to stay clear and stable across daily, weekly, and monthly use.

## Why This Exists

A role can be worthwhile even when a company is imperfect.

A company can look promising while giving the user weak growth.

This skill helps make that distinction visible through repeated, evidence-based check-ins.

## License

MIT

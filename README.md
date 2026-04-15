# Company Growth Check-In

`company-growth-check-in` is a reusable AI skill for one ongoing question:

**Is this company or role still worth staying in, and am I still getting meaningful growth from staying?**

It is designed for people who want better career judgment over time, not just a one-off reaction to a bad day.

## What It Does

The skill supports three modes:

- **Bootstrap mode**: gather context about the company, the role, and the user's goals
- **Discussion mode**: run an agent-led check-in where the agent asks focused questions one at a time
- **Review mode**: synthesize saved daily reports into weekly or monthly reviews

The output is meant to help with decision quality, not loyalty, morale, or generic journaling.

## Core Question

The skill keeps returning to two questions:

- Is this company or role still worth staying in?
- Is the user still getting meaningful growth from staying?

## Repository Structure

```text
company-growth-check-in/
├── SKILL.md
├── README.md
├── .gitignore
├── agents/
│   └── openai.yaml
├── context/
│   └── .gitkeep
├── reports/
│   └── .gitkeep
└── references/
    ├── assessment-framework.md
    ├── bootstrap-template.md
    ├── daily-report-template.md
    └── review-template.md
```

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

# Credit Card Skills

Agent skills for credit-card rewards planning, card matching, application sequencing, Chase 5/24-aware strategy, and monthly benefit reminders.

> This project is for educational and informational purposes only. It is not financial, legal, tax, or credit repair advice. Credit-card offers and issuer rules change often; agents using this skill should verify current public sources.

## Quick Start

### Claude Code / Compatible Plugin CLI

Install all plugins from this repository:

```bash
npx plugins add YOUR-USERNAME/credit-card-skills
```

Install only the credit-card rewards plugin:

```bash
npx plugins add YOUR-USERNAME/credit-card-skills --plugin credit-card-rewards
```

### Individual Skills CLI

Install the skills from this repository:

```bash
npx skills add YOUR-USERNAME/credit-card-skills
```

Install for another supported agent:

```bash
npx skills add YOUR-USERNAME/credit-card-skills -a <agent-name>
```

Replace `YOUR-USERNAME` with the GitHub account or organization that owns the published repo.

## Available Plugins

### Credit Card Rewards (`credit-card-rewards`)

Research current credit-card offers, compare rewards and welcome bonuses, build Chase 5/24-aware application paths, and design benefit reminder workflows.

| Skill | Description |
| --- | --- |
| `credit-card-rewards-planner` | Finds and compares rewards cards, travel cards, airline/hotel cards, 0% APR cards, usage benefits, welcome bonuses, and application paths. |

## Manual Install

If you do not use the plugin CLI, clone the repo and copy the skill into your Codex skills directory:

```bash
git clone https://github.com/YOUR-USERNAME/credit-card-skills.git
cd credit-card-skills
mkdir -p ~/.codex/skills
cp -R plugins/credit-card-rewards/skills/credit-card-rewards-planner ~/.codex/skills/
```

Restart Codex or start a new session so the skill metadata is loaded.

## Test Without Installing

You can reference the skill folder directly from a local checkout:

```text
Use $credit-card-rewards-planner at /path/to/credit-card-skills/plugins/credit-card-rewards/skills/credit-card-rewards-planner to build a Chase 5/24-aware card application path.
```

## Example Prompts

```text
Use $credit-card-rewards-planner to compare the highest current welcome-bonus credit cards for someone who spends $4,000 per month.
```

```text
Use $credit-card-rewards-planner to find a zero-interest credit card for a large upcoming purchase and explain the tradeoffs.
```

```text
Use $credit-card-rewards-planner to create monthly reminders for my current card credits, annual fees, and bonus deadlines.
```

## Repository Structure

```text
.
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   └── credit-card-rewards/
│       ├── plugin.json
│       └── skills/
│           └── credit-card-rewards-planner/
│               ├── SKILL.md
│               ├── agents/openai.yaml
│               └── references/
└── README.md
```

## Before Publishing

Update these placeholders:

- `YOUR-USERNAME` in `README.md`.
- `YOUR-NAME` in `.claude-plugin/marketplace.json`.
- `YOUR-NAME`, `homepage`, and `repository` in `plugins/credit-card-rewards/plugin.json`.

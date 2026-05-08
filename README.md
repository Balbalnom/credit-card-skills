# Credit Card Skills

Agent skills for credit-card rewards planning, card matching, application sequencing, Chase 5/24-aware strategy, and monthly benefit reminders.

> This project is for educational and informational purposes only. It is not financial, legal, tax, or credit repair advice. Credit-card offers and issuer rules change often; agents using this skill should verify current public sources.

## OpenAI / Codex Pattern

This repository follows the Codex plugin layout used by OpenAI's plugin examples:

- Repo marketplace: `.agents/plugins/marketplace.json`
- Plugin folder: `plugins/credit-card-rewards/`
- Plugin manifest: `plugins/credit-card-rewards/.codex-plugin/plugin.json`
- Bundled skills: `plugins/credit-card-rewards/skills/`

OpenAI's Codex docs describe skills as the authoring format and plugins as the installable distribution unit for reusable skills. For local authoring, Codex can also read direct skill folders from `.agents/skills` and user skill folders.

## Install In Codex

### Install With `npx plugins add`

```bash
npx plugins add Balbalnom/credit-card-skills
```

Install only this plugin:

```bash
npx plugins add Balbalnom/credit-card-skills --plugin credit-card-rewards
```

That command does not install a bare `SKILL.md` directly. It reads `.claude-plugin/marketplace.json`, downloads the plugin from `plugins/credit-card-rewards`, then exposes the bundled skill from `plugins/credit-card-rewards/skills/credit-card-rewards-planner`.

For installers that support direct skill installation:

```bash
npx skills add Balbalnom/credit-card-skills
```

### Codex App

1. Open the Codex plugin directory.
2. Add or select the marketplace for this repository after it is published.
3. Install `credit-card-rewards`.
4. Start a new thread and invoke the plugin or its bundled skill.

### Codex CLI

Open Codex and use the plugin browser:

```bash
codex
/plugins
```

In the plugin browser, select the marketplace for this repository, open `credit-card-rewards`, and install it.

## Manual Local Marketplace

For local testing before publishing, clone this repo and keep the marketplace file at `.agents/plugins/marketplace.json`:

```bash
git clone https://github.com/Balbalnom/credit-card-skills.git
cd credit-card-skills
codex
/plugins
```

The marketplace entry points to `./plugins/credit-card-rewards`, which contains the `.codex-plugin/plugin.json` manifest and bundled skill.

## Manual Skill Install

If you only want the skill without plugin packaging, copy it into a Codex skills location:

```bash
git clone https://github.com/Balbalnom/credit-card-skills.git
cd credit-card-skills
mkdir -p ~/.agents/skills
cp -R plugins/credit-card-rewards/skills/credit-card-rewards-planner ~/.agents/skills/
```

Restart Codex or start a new session so the skill metadata is loaded.

## Test Without Installing

You can reference the skill folder directly from a local checkout:

```text
Use $credit-card-rewards-planner at /path/to/credit-card-skills/plugins/credit-card-rewards/skills/credit-card-rewards-planner to build a Chase 5/24-aware card application path.
```

## Available Plugin

### Credit Card Rewards (`credit-card-rewards`)

Research current credit-card offers, compare rewards and welcome bonuses, build Chase 5/24-aware application paths, and design benefit reminder workflows.

| Skill                         | Description                                                                                                                                |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `credit-card-rewards-planner` | Finds and compares rewards cards, travel cards, airline/hotel cards, 0% APR cards, usage benefits, welcome bonuses, and application paths. |

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
├── .agents/
│   └── plugins/
│       └── marketplace.json
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   └── credit-card-rewards/
│       ├── .codex-plugin/
│       │   └── plugin.json
│       ├── plugin.json
│       └── skills/
│           └── credit-card-rewards-planner/
│               ├── SKILL.md
│               ├── agents/openai.yaml
│               └── references/
└── README.md
```

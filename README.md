# Credit Card Skills

Agent skills for credit-card rewards planning, card matching, application sequencing, Chase 5/24-aware strategy, monthly benefit reminders, and card-linked discount discovery.

> This project is for educational and informational purposes only. It is not financial, legal, tax, or credit repair advice. Credit-card offers and issuer rules change often; agents using this skill should verify current public sources.

## OpenAI / Codex Pattern

This repository follows the Codex plugin layout used by OpenAI's plugin examples:

- Repo marketplace: `.agents/plugins/marketplace.json`
- Plugin folders: `plugins/credit-card-rewards/`, `plugins/credit-card-discounts/`
- Plugin manifests: `plugins/<plugin-name>/.codex-plugin/plugin.json`
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

Install only the discount finder plugin:

```bash
npx plugins add Balbalnom/credit-card-skills --plugin credit-card-discounts
```

That command does not install a bare `SKILL.md` directly. It reads `.claude-plugin/marketplace.json`, downloads the selected plugin from `plugins/`, then exposes the bundled skill from that plugin's `skills/` directory.

For installers that support direct skill installation:

```bash
npx skills add Balbalnom/credit-card-skills
```

### Codex App

1. Open the Codex plugin directory.
2. Add or select the marketplace for this repository after it is published.
3. Install `credit-card-rewards` or `credit-card-discounts`.
4. Start a new thread and invoke the plugin or its bundled skill.

### Codex CLI

Open Codex and use the plugin browser:

```bash
codex
/plugins
```

In the plugin browser, select the marketplace for this repository, open the plugin you want, and install it.

## Manual Local Marketplace

For local testing before publishing, clone this repo and keep the marketplace file at `.agents/plugins/marketplace.json`:

```bash
git clone https://github.com/Balbalnom/credit-card-skills.git
cd credit-card-skills
codex
/plugins
```

The marketplace entries point to `./plugins/credit-card-rewards` and `./plugins/credit-card-discounts`, each containing a `.codex-plugin/plugin.json` manifest and bundled skills.

## Manual Skill Install

If you only want the skill without plugin packaging, copy it into a Codex skills location:

```bash
git clone https://github.com/Balbalnom/credit-card-skills.git
cd credit-card-skills
mkdir -p ~/.agents/skills
cp -R plugins/credit-card-rewards/skills/credit-card-rewards-planner ~/.agents/skills/
cp -R plugins/credit-card-discounts/skills/card-linked-discount-finder ~/.agents/skills/
```

Restart Codex or start a new session so the skill metadata is loaded.

## Test Without Installing

You can reference the skill folder directly from a local checkout:

```text
Use $credit-card-rewards-planner at /path/to/credit-card-skills/plugins/credit-card-rewards/skills/credit-card-rewards-planner to build a Chase 5/24-aware card application path.
```

```text
Use $card-linked-discount-finder at /path/to/credit-card-skills/plugins/credit-card-discounts/skills/card-linked-discount-finder to find stackable discounts for a Nike purchase.
```

## Available Plugins

### Credit Card Rewards (`credit-card-rewards`)

Research current credit-card offers, compare rewards and welcome bonuses, build Chase 5/24-aware application paths, and design benefit reminder workflows.

| Skill                         | Description                                                                                                                                |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `credit-card-rewards-planner` | Finds and compares rewards cards, travel cards, airline/hotel cards, 0% APR cards, usage benefits, welcome bonuses, and application paths. |

### Credit Card Discounts (`credit-card-discounts`)

Find card-linked offers, issuer discounts, shopping portal deals, merchant promotions, coupon compatibility, and stackable savings for planned purchases.

Useful trigger phrases include: discount, coupon, promo code, cash back, shopping portal, Rakuten, TopCashback, Capital One Shopping, Amex Offers, Chase Offers, Citi Merchant Offers, BankAmeriDeals, statement credit, card-linked offer, best card for a brand, which card should I use, stack discounts, and find offers for my cards.

| Skill                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `card-linked-discount-finder` | Matches cards and desired brands in both directions: best discounts for a brand, or best brands/offers for a user's current cards. |

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

```text
Use $card-linked-discount-finder to find the best discounts for a purchase at Apple using my Chase, Amex, and Capital One cards.
```

```text
Use $card-linked-discount-finder to list brands where my current credit cards may have targeted or public offers this month.
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
│   └── credit-card-discounts/
│       ├── .codex-plugin/
│       │   └── plugin.json
│       ├── plugin.json
│       └── skills/
│           └── card-linked-discount-finder/
│               ├── SKILL.md
│               ├── agents/openai.yaml
│               └── references/
└── README.md
```

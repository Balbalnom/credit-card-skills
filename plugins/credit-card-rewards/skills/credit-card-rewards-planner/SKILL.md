---
name: credit-card-rewards-planner
description: >
  Find and compare rewards credit cards, welcome bonuses, travel cards, airline
  and hotel cards, zero-interest cards, category earn rates, credits, and
  cardholder benefits; build credit-card application sequencing plans, including
  Chase 5/24-aware paths and benefit reminder workflows. Use when Codex needs to
  research current card offers, match cards to a user's spend and travel needs,
  optimize a credit-card rewards journey, or design monthly reminders for card
  benefits, credits, annual fees, and bonus deadlines.
---

# Credit Card Rewards Planner

## Overview

Use this skill to help users evaluate credit cards, rewards programs, welcome bonuses, 0% APR offers, travel perks, and application sequencing. Treat offers, fees, rules, transfer partners, and benefits as time-sensitive; verify current data from primary issuer pages and reputable current comparison sources before recommending cards.

## Guardrails

- Do not present output as financial, legal, tax, or credit repair advice. Frame recommendations as educational options based on the user's stated facts and current public offers.
- Do not encourage users to apply for credit they cannot repay in full or manage responsibly.
- Do not infer sensitive facts. Ask for or clearly state assumptions about monthly spend, travel goals, home airport, preferred airlines/hotels, existing cards, recent approvals, credit score band, business-card eligibility, and comfort with annual fees.
- Do not guarantee approval, credit limits, bonus eligibility, card retention offers, or rule outcomes.
- Use exact dates when discussing application timing, bonus deadlines, statement credits, annual fees, or 5/24 windows.

## Workflow

1. Clarify the objective: highest welcome bonus, daily spend rewards, travel/airline/hotel perks, 0% APR, balance transfer, beginner setup, premium travel, business-card path, or Chase 5/24-aware sequencing.
2. Collect user context using the intake checklist in `references/intake-and-output.md`.
3. Research current offers and rules using `references/research.md`. Browse when available because credit-card offers and issuer rules change frequently.
4. Normalize card economics: welcome bonus value, minimum spend, annual fee, credits, earning categories, transfer value assumptions, foreign transaction fee, lounge or travel benefits, 0% APR duration and fees, and downgrade/keeper options.
5. Match cards to the user's goals and constraints. Prefer transparent tradeoffs over single-score rankings.
6. Build an application path using `references/strategy-and-524.md` when sequencing matters.
7. If the user wants reminders, design a monthly benefit and deadline system using `references/reminders.md`.

## Output Standards

Include:

- A concise summary of the best-fit cards or path.
- A comparison table with source links and "last checked" date.
- Assumptions and value estimates.
- Risks, exclusions, and rule uncertainty.
- Next actions with exact dates when timing matters.

For card rankings, separate:

- Highest theoretical value.
- Best practical fit for the user's spend.
- Best low-complexity option.
- Cards to avoid or delay, with reasons.

## References

- Read `references/intake-and-output.md` for user intake questions and response templates.
- Read `references/research.md` for current-offer research and sourcing rules.
- Read `references/strategy-and-524.md` for credit-card journey planning and Chase 5/24-aware sequencing.
- Read `references/reminders.md` for calendar, cron, and email reminder designs.

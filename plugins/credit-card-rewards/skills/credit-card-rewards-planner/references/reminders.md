# Reminders

Use this reference when the user wants recurring reminders for credit-card benefits, statement credits, annual fees, minimum-spend deadlines, or offer expirations.

## Reminder Inventory

Build a table with:

- Card.
- Benefit or deadline.
- Amount or value.
- Frequency.
- Reset date or statement-cycle dependency.
- Enrollment requirement.
- Redemption method.
- Reminder date.
- Owner.
- Notes.

Common reminders:

- Monthly dining, rideshare, streaming, airline, hotel, or shopping credits.
- Quarterly category activation.
- Annual travel credit.
- Annual free night, companion certificate, or checked-bag perk.
- Lounge guest policy changes.
- Minimum-spend deadline for welcome bonus.
- Annual fee posting and retention-call window.
- Downgrade or cancel decision date.
- 0% APR payoff checkpoints.

## Calendar Design

Prefer calendar reminders for most users:

- Create one monthly recurring reminder for each use-it-or-lose-it credit.
- Create one deadline reminder 30, 14, and 3 days before a welcome-bonus minimum-spend deadline.
- Create one annual-fee review reminder 30 days before the expected annual-fee anniversary.
- Include the card name, benefit, amount, and action in the event title.

Example event title:

`Use Amex Gold dining credit - $10 before month end`

## Cron Design

Use cron only when the user has a machine or server that runs reliably. For macOS laptops, mention that cron may not run while asleep and that calendar reminders are usually more reliable.

Basic monthly cron pattern:

```cron
0 9 1 * * /path/to/reminder-script
```

For email, recommend a script that sends through an authenticated provider or local mail setup. Do not invent credentials. Ask what email service or notification tool the user wants to use.

## Email Content

Monthly email should include:

- Benefits expiring this month.
- Credits already used, if the user tracks them.
- Minimum-spend progress and deadline.
- Annual fees posting in the next 60 days.
- Cards to consider next only if timing is relevant.

Keep the subject actionable:

`Credit card benefits for May 2026`

## Automation Caution

Do not ask users to store credit-card numbers, passwords, or bank credentials in reminder scripts. If tracking transactions, recommend privacy-preserving manual checkboxes or a reputable personal finance tool with user-controlled permissions.

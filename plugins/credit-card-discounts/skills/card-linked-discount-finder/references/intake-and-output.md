# Intake And Output

## Intake

Ask only for details needed for the user's request.

Brand-first inputs:

- Merchant or brand name.
- Product or category.
- Online, in-store, app, pickup, delivery, or travel booking channel.
- Purchase amount and target purchase date.
- User's cards or issuers, if they want card-specific matching.
- Memberships: loyalty program, student, military, employee, warehouse club, airline/hotel status.

Card-first inputs:

- Issuers and card names, not card numbers.
- Whether the user can check targeted offers in issuer apps.
- Preferred brands or categories.
- Time horizon: today, this week, this month, upcoming trip, or holiday shopping.

Purchase-first inputs:

- Product requirements.
- Acceptable retailers.
- Budget and deadline.
- Return policy importance.
- Warranty or purchase protection needs.

## Output Tables

Use columns relevant to the request:

- Merchant or brand.
- Offer source.
- Eligible card or issuer.
- Savings type.
- Estimated value.
- Cap.
- Minimum purchase.
- Enrollment or click-through requirement.
- Channel: online, app, in-store, portal, wallet.
- Expiration.
- Stackability.
- Source.
- Last checked.

## Response Shape

For a single brand:

1. State best checkout path.
2. Show all found offers and why they do or do not stack.
3. Give activation steps in order.
4. Add backup plan if targeted offers are unavailable.

For card-first:

1. Group offers by issuer or card.
2. Highlight expiring and high-value offers.
3. Separate confirmed public offers from user-verified targeted offers.
4. Suggest reminders for expiring benefits.

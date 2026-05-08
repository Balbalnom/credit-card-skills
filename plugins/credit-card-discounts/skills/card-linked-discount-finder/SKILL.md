---
name: card-linked-discount-finder
description: >
  Find discounts, card-linked offers, statement credits, issuer shopping offers,
  shopping portal rewards, merchant promotions, coupon codes, and stackable
  purchase savings based on a user's credit cards and desired brand, or in the
  reverse direction by identifying brands and merchants that have current offers
  for the user's cards. Use when Codex needs to compare which card to use for a
  planned purchase, find brand-specific savings, or build a checklist for
  activating and stacking credit-card discounts. Trigger for user phrases such
  as discount, coupon, promo code, cash back, cashback, shopping portal, portal
  bonus, Rakuten, TopCashback, Capital One Shopping, PayPal Honey, Amex Offers,
  Chase Offers, Citi Merchant Offers, BankAmeriDeals, targeted offer, statement
  credit, card-linked offer, card offer, merchant offer, best card for a brand,
  which card should I use, stack offers, stack discounts, save money at a brand,
  brand deal, retailer deal, purchase discount, and find offers for my cards.
---

# Card Linked Discount Finder

## Overview

Use this skill to help users find current discounts and stackable savings tied to their credit cards, issuers, shopping portals, and desired brands. Treat all offers as time-sensitive and often targeted; verify current public information and tell users when they must confirm personalized offers inside their own issuer account.

## Guardrails

- Do not ask for card numbers, login credentials, one-time passwords, or screenshots containing sensitive account data.
- Do not claim that a targeted offer is available to the user unless the user confirms it appears in their account.
- Do not bypass paywalls, logins, CAPTCHAs, app-only flows, or offer enrollment controls.
- Do not rely on coupon blogs, affiliate pages, or scraped snippets without cross-checking against issuer, merchant, or portal sources when possible.
- Do not present affiliate links as neutral sources. Prefer direct issuer, merchant, or portal pages.
- State exact "last checked" dates and expiration dates when known.
- Explain stackability uncertainty. Merchant promos, portals, card-linked offers, coupons, gift cards, and wallets can conflict.

## Workflow

1. Determine direction:
   - Brand-first: user wants to buy from a brand and needs the best card, offer, portal, or stack.
   - Card-first: user has cards and wants to know which merchants currently have useful discounts.
   - Purchase-first: user has a product/category and wants a savings plan across cards and stores.
2. Collect only needed context using `references/intake-and-output.md`.
3. Research current offers using `references/source-policy.md`.
4. Normalize each offer: discount type, trigger, eligible card or issuer, enrollment requirement, expiration, cap, exclusions, online/in-store support, and stackability.
5. Rank by practical net savings, not headline percentage.
6. Produce an activation and checkout checklist.

## Output Standards

Include:

- Best option summary.
- Offer comparison table with source links and last checked date.
- Required actions: activate, enroll, click portal, use promo code, pay with specific card, or avoid wallet.
- Stackability notes and exclusions.
- Expiration dates and reminder suggestions.
- Verification steps for targeted offers.

When no reliable offer is found, say that clearly and suggest safe next checks such as issuer app offers, merchant email signup, official loyalty program, and reputable portal comparison tools.

## References

- Read `references/intake-and-output.md` for context questions and response templates.
- Read `references/source-policy.md` for external-source rules.
- Read `references/offer-matching.md` for ranking and stackability logic.

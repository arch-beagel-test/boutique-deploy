# Ask currencyservice for every conversion

- **Status:** Accepted
- **Date:** 2026-06-01
- **Applies to:** boutique-frontend, boutique-checkoutservice, boutique-currencyservice
- **Deciders:** @arch-beagel-test/platform

## Context

The cache in cross/0006 showed one price on the product page and charged another at checkout.

## Decision

Every service asks currencyservice for each conversion. currencyservice is the only service that reads the rates in `data/currency_conversion.json`. Supersedes cross/0006.

## Consequences

currencyservice must stay fast: it keeps the rates in memory.

# Convert currency from a cache in the frontend

- **Status:** Superseded by cross/0007
- **Date:** 2026-05-04
- **Applies to:** boutique-frontend, boutique-currencyservice
- **Deciders:** @arch-beagel-test/platform

## Context

Every product page asked currencyservice for each price, which was slow under load.

## Decision

The frontend cached the conversion table for an hour.

## Consequences

Prices drifted from checkout's, which asks currencyservice itself. Superseded by cross/0007.

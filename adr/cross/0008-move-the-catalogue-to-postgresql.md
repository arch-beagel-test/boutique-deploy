# Move the product catalogue to PostgreSQL

- **Status:** Proposed
- **Date:** 2026-09-15
- **Applies to:** boutique-productcatalogservice, boutique-recommendationservice
- **Deciders:** @arch-beagel-test/platform

## Context

The catalogue is a JSON file baked into the image. Changing a price means a release.

## Decision

productcatalogservice reads products from its own PostgreSQL database. Only productcatalogservice opens it; recommendationservice keeps asking productcatalogservice over gRPC.

## Consequences

A migration job and a backup for one more database.

review-by: 2026-10-31

## Questions for the owner

1. **Do we keep products.json as a fallback?** If the database is down, should the service start from the file?
2. **Who runs the database?** The storefront team, or platform?

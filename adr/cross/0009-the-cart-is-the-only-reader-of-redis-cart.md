# The cart is the only reader of redis-cart

- **Status:** Accepted
- **Date:** 2026-03-16
- **Applies to:** boutique-cartservice, boutique-deploy.redis-cart
- **Deciders:** @arch-beagel-test/platform

## Context

redis-cart is in the cluster and any pod can reach it.

## Decision

Only boutique-cartservice reads or writes redis-cart. Any other service that needs a cart asks cartservice's GetCart over gRPC.

## Consequences

A NetworkPolicy in boutique-deploy keeps other pods out.

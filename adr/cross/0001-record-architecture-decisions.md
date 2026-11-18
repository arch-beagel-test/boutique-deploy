# Record architecture decisions

- **Status:** Accepted
- **Date:** 2026-03-02
- **Applies to:** every boutique repository
- **Deciders:** @arch-beagel-test/platform

## Context

The shop is ten services in ten repositories, owned by three teams. Decisions that bind more than one repository need one place.

## Decision

Decisions that bind more than one service live in `boutique-deploy/adr/cross/`. A decision that binds one service lives in that repository's `docs/adr/`.

## Consequences

Every team reads `adr/cross/` before changing how services talk to each other.

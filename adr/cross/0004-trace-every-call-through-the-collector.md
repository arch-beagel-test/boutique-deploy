# Trace every call through the OpenTelemetry collector

- **Status:** Accepted
- **Date:** 2026-04-14
- **Applies to:** every service, boutique-deploy.opentelemetrycollector
- **Deciders:** @arch-beagel-test/platform

## Context

Errors across services were hard to follow without a trace that spans every hop.

## Decision

Every service exports traces to the OpenTelemetry collector deployed by boutique-deploy, when `ENABLE_TRACING=1`. No service sends telemetry to a vendor directly.

## Consequences

The collector is the one place that knows the vendor.

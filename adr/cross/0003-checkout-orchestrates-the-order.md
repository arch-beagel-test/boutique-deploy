# Checkout orchestrates the order

- **Status:** Accepted
- **Date:** 2026-03-09
- **Applies to:** boutique-checkoutservice, boutique-frontend, boutique-paymentservice, boutique-emailservice, boutique-shippingservice
- **Deciders:** @arch-beagel-test/platform

## Context

Placing an order touches the cart, prices, currency, payment, shipping and email. If the frontend called each of these itself, a failure halfway would leave a charged card and no order.

## Decision

Only boutique-checkoutservice calls paymentservice, shippingservice's ShipOrder and emailservice. The frontend calls `PlaceOrder` once and shows the result. Nothing calls checkoutservice except the frontend.

## Consequences

- The frontend never imports a payment or email client.
- Payment, shipping and email never call back into checkout.

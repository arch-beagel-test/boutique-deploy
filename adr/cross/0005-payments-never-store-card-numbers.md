# Payments never store card numbers

    - **Status:** Accepted
    - **Date:** 2026-04-20
    - **Applies to:** boutique-paymentservice, boutique-checkoutservice, boutique-frontend
    - **Deciders:** @arch-beagel-test/platform

    ## Context

    Card data puts every service that holds it in PCI scope.

    ## Decision

    Only boutique-paymentservice sees a card number, in memory, for one Charge call. It returns a transaction ID. No service logs, stores or forwards a card number, and no datastore has a column for one.

    ## Consequences

    - Logs mask the card number to its last four digits.
- The frontend sends card details to checkout once, inside PlaceOrder.

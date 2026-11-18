# Services talk over gRPC with one shared proto

    - **Status:** Accepted
    - **Date:** 2026-03-02
    - **Applies to:** boutique-frontend, boutique-checkoutservice, boutique-cartservice, boutique-paymentservice, boutique-currencyservice, boutique-shippingservice, boutique-emailservice, boutique-productcatalogservice, boutique-recommendationservice
    - **Deciders:** @arch-beagel-test/platform

    ## Context

    Services are written in Go, C#, Node.js and Python. They need one contract every language can generate code from.

    ## Decision

    Every service-to-service call is gRPC, defined in `protos/demo.proto` in boutique-deploy. Each service generates its stubs with `genproto.sh`. No service calls another over plain HTTP or reads another's database.

    ## Consequences

    - A new call starts as a change to `protos/demo.proto`, reviewed by the platform team.
- A service never imports another service's code or opens another service's datastore.

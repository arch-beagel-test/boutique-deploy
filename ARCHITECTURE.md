# Online Boutique architecture

Ten services, each in its own repository, deployed together from boutique-deploy.

| Service | Language | Team | Talks to |
|---|---|---|---|
| boutique-frontend | Go | storefront | product catalogue, currency, cart, recommendations, shipping (quotes), checkout, ads |
| boutique-checkoutservice | Go | checkout | cart, product catalogue, currency, shipping, payment, email |
| boutique-cartservice | C# | checkout | redis-cart |
| boutique-productcatalogservice | Go | storefront | products.json |
| boutique-currencyservice | Node.js | checkout | its rates file |
| boutique-paymentservice | Node.js | checkout | nothing |
| boutique-shippingservice | Go | checkout | nothing |
| boutique-emailservice | Python | checkout | nothing |
| boutique-recommendationservice | Python | storefront | product catalogue |

The rules that bind services are in `adr/cross/`: gRPC only (cross/0002), checkout orchestrates (cross/0003), only the cart reads redis-cart (cross/0009).

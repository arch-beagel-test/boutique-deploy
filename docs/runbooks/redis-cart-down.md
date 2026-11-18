# Runbook: redis-cart is down

Symptoms: the cart page errors, checkout fails at GetCart.

1. `kubectl get pods -l app=redis-cart`; restart the pod if it's in CrashLoopBackOff.
2. Carts are lost on restart: that's accepted (cross/0009 keeps the cart in one store).
3. If it keeps failing, switch cartservice to Spanner with `SPANNER_PROJECT` (see boutique-cartservice docs/adr/0001).

# Runbook: roll back a release

1. Find the last good tag in `release/`.
2. `kubectl apply -f release/kubernetes-manifests.yaml` from that tag.
3. Check the frontend's `/_healthz` and place a test order.
4. Post in #boutique-ops what was rolled back and why.

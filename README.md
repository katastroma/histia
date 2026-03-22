# Histia

Katastroma's provisioner. Implements the
[katartismos](https://github.com/katastroma/katartismos) interface.

Given manifests, labels, and a service account identity, histia applies the
manifests to the cluster using server-side apply, stamps all applied resources
with the given labels, and prunes any labeled resources no longer in the
manifest set.

Histia applies manifests in the order it receives them. It does not reorder —
callers are responsible for providing manifests in a safe apply order.

## RBAC

Histia's own SA requires:

- `impersonate` on service accounts — to impersonate tenant deployer SAs for all
  mutations (create, patch, delete via SSA)
- `list` on all resources — to query the cluster by label for pruning diffs.
  Histia uses its own SA for reads and impersonates the tenant SA for mutations.

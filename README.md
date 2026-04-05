# Histia

Provisioner implementation. Implements the
[katartismos](https://github.com/katastroma/katartismos) interface.

Receives manifests via gRPC streaming and applies them to the cluster using
server-side apply. Impersonates the tenant's provisioner ServiceAccount
(`system:serviceaccount:<tenant-namespace>:provisioner`).

Before applying each manifest, verifies the resource type supports the `list`
verb via the Kubernetes discovery API. Types that cannot be listed are rejected
— they cannot be pruned and would be orphaned.

Verifies the source target lease before applying.

Streams applied manifests to the next pipeline stage.

## RBAC

Histia's platform SA requires `impersonate` on ServiceAccounts.

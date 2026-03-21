# Histia

Katastroma's provisioner. Implements the
[katartismos](https://github.com/katastroma/katartismos) gRPC service.

Given manifests, histia applies them to the cluster using server-side apply with
Kubernetes impersonation. Prunes resources labeled with the tenant's identity
that are no longer present in the current render.

## Ecosystem

- **[Phortizo](https://github.com/katastroma/phortizo)** — retriever, implements
  [naukleros](https://github.com/katastroma/naukleros)
- **[Orpheus](https://github.com/katastroma/orpheus)** — renderer, implements
  [keleustēs](https://github.com/katastroma/keleustes)
- **Histia** (this) — provisioner, implements
  [katartismos](https://github.com/katastroma/katartismos)

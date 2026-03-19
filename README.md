# Histia

Katastroma's reference provisioner. Implements the
[katartismos](https://github.com/katastroma/katartismos) interface.

Given a resource inventory, histia applies, deletes, or diffs resources directly
against the Kubernetes API using server-side apply. No external dependencies, no
running services — just the cluster.

## What This Is

A Go module that implements the katartismos provisioner interface. Consumed as a
dependency by orchestrators like
[pedalion](https://github.com/katastroma/pedalion) that need to provision
resources against a cluster.

## Ecosystem

Histia is one of two reference implementations provided by
[katastroma](https://github.com/katastroma):

- **[Orpheus](https://github.com/katastroma/orpheus)** — reference resolver,
  implements [keleustēs](https://github.com/katastroma/keleustes)
- **Histia** (this) — reference provisioner, implements
  [katartismos](https://github.com/katastroma/katartismos)

# SFR: Weighted Multi-Column Vector Search

This repository contains publicly releasable implementation components and
experimental artifacts for **SFR**, a framework for efficient weighted
multi-column vector search.

SFR supports similarity search over multiple vector columns with
query-dependent weights. It improves the recall-throughput trade-off through
candidate reuse, compressed score estimation, selective exact reranking, and
adaptive search-resource allocation.

## Overview

In weighted multi-column vector search, each data object is represented by
multiple vector columns corresponding to different features, attributes, or
modalities. A query is encoded into multiple query vectors, one for each
participating vector column. The resulting per-column similarities are
aggregated using query-dependent weights to produce the final ranking.

SFR is designed to efficiently support this setting using independent
disk-based vector indexes. Its main components include:

- **Candidate reuse:** reuses points already visited and evaluated during graph
  traversal to improve candidate coverage with little additional search effort.
- **Compressed score estimation:** estimates missing cross-column similarities
  using compact in-memory representations, reducing accesses to full-precision
  vectors.
- **Selective exact reranking:** uses score bounds to identify candidates that
  may affect the final ranking and selectively computes their exact scores.
- **Adaptive search-resource allocation:** distributes search effort across
  vector columns according to their expected contributions to the final
  ranking.

## Note on Implementation

Parts of the original experimental implementation rely on proprietary or
commercial code and therefore cannot be released publicly.

We will make the publicly releasable components of SFR available in this
repository, together with relevant experimental configurations and
documentation. For components that depend on non-public code, we may explore
replacing them with publicly available open-source alternatives, subject to
implementation feasibility and licensing constraints. Such replacements may be
added in future updates to provide a more complete open-source implementation
of SFR.

## Datasets

The experiments use multiple real-world datasets containing several vector
columns per object.

Due to the size and licensing conditions of some datasets, processed vector
data may not be distributed directly through this repository. Where applicable,
we plan to provide information or instructions for obtaining the original
datasets and preparing the vector representations used in the experiments.

## Reproducibility

Where possible, this repository will include publicly releasable materials
related to the experiments, such as configurations, workload settings,
evaluation scripts, and instructions for reproducing selected experimental
results.

The extent of full end-to-end reproducibility may depend on the availability of
open-source replacements for components that rely on non-public code.

## Artifact Status

This repository is currently being prepared as the artifact repository for the
SFR paper. Publicly releasable components, documentation, and experimental
materials will be added as they are finalized.

## License

Licensing information will be provided for released components where
applicable, subject to the licenses and redistribution requirements of the
underlying open-source dependencies.

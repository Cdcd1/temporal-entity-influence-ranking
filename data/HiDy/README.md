# HiDy data card

## Source and attribution

Original dataset: *HiDy: A Large-scale Hierarchical Dynamic Financial Knowledge Base*, version 1.10, published 3 July 2024. Creators: Xinyi Zhu, Jiawei Li, Hao Wang, Liping Wang, Boliang Li, Yanyan Shen, and Lei Chen. Source: [Zenodo DOI 10.5281/zenodo.12630355](https://doi.org/10.5281/zenodo.12630355). License: [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).

`raw/data.zip` is the unmodified Zenodo `data.zip` archive. Its MD5 checksum is `a1e4b0969697706c286eecc9d593c3da`, matching the Zenodo file record. Its SHA-256 checksum is in the repository root `SHA256SUMS`.

## Derived task package

The files in `task/` were generated from the HiDy release for the manuscript's point-in-time ranking task. They are a transformed research dataset, not part of the original HiDy release. The source event and node records were normalized into the project's temporal heterogeneous graph schema. Candidate sets and labels were then generated using historical cutoffs and subsequent observation windows.

| File | Contents |
| --- | --- |
| `nodes.parquet` | Normalized entities and types |
| `events.parquet` | Normalized time-stamped relation events |
| `state_edges.parquet` | Relations represented as validity intervals |
| `relation_semantics.yaml` | Relation direction and event/state interpretation |
| `cutoffs.parquet` | Training, validation, and later-window cutoff boundaries |
| `candidates.parquet` | Candidate entities at each cutoff |
| `labels.parquet` | Derived temporal reachability ranking labels |

The ranking-label generator used a maximum strictly increasing temporal path depth of three, fact-level deduplication, and candidate types `company` and `securities_company`. The task package contains 8,917 candidate/label rows. The exact stored cutoff values and windows are in `cutoffs.parquet`; no positive gap was inserted between each cutoff and its label window. The repository checksum file records the bytes of this release.

[`task_protocol.json`](task_protocol.json) also gives the task parameters, relation directions, and cutoff values in a portable text format without server-local paths.

The source archive and the derived files are provided with attribution to the original HiDy creators under CC BY 4.0. Please cite the original Zenodo record when using these data.

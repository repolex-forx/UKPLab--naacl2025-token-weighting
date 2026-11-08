# Repolex Knowledge Graph of UKPLab/naacl2025-token-weighting

RDF knowledge graph data for [UKPLab/naacl2025-token-weighting](https://github.com/UKPLab/naacl2025-token-weighting), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download UKPLab/naacl2025-token-weighting
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0b2445496fe961bd913e2b96e01ec49570867d7c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0b2445496fe961bd913e2b96e01ec49570867d7c
│           └── chunk-001.nq.gz
├── blob
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4970fb1afe75d7716e27b50972676694512c4ece.nq.gz
│   ├── 4bc8f52aeb686cf8f7b94b6de5bbabde54ebc22c.nq.gz
│   ├── 5208477f0508586a16c8b08b1b8decb0facff778.nq.gz
│   ├── 653ee10c0e463cd611263c8b95bed3593aba2b35.nq.gz
│   ├── 73a8b18c4eb05700ad77ac182221923aeb318fb7.nq.gz
│   ├── 78adf6d3c4f21b9212b9b528fd7ef7ad415b6312.nq.gz
│   ├── 942e623c1b9b9019b28a55ee24e59c9eb2ba38f3.nq.gz
│   ├── 94a0ec8b1b1e4226fa0f4bd9e853902fff7f6769.nq.gz
│   ├── 962f03473dcb72fe54eee217960ad41cbd3971fe.nq.gz
│   ├── a102b4c11023cbfc814b662a0b467f989c71530e.nq.gz
│   ├── baf3b7b76b4bbc8d93ed801b5b12ab6f3115fc7d.nq.gz
│   ├── d1684018f5391d6c76ffcc6038ba0a25290af331.nq.gz
│   ├── d8b779adeed10fbc49a4b14a6070c27a26e7c0bc.nq.gz
│   ├── d8fb4b338efd3ffe7e3f14a83aa6d4a7ea3118e0.nq.gz
│   ├── dbbf88f06790ba0de4191122afcc9048e05d7b34.nq.gz
│   └── dea401196b0d225826153c3e458d7f33cf55bb0d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0b2445496fe961bd913e2b96e01ec49570867d7c.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[UKPLab/naacl2025-token-weighting](https://github.com/UKPLab/naacl2025-token-weighting)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*

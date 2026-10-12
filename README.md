# Repolex Knowledge Graph of datasette/datasette-litestream

RDF knowledge graph data for [datasette/datasette-litestream](https://github.com/datasette/datasette-litestream), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-litestream
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6d043ddcafee3b2bfd1db05460cde8d6a86461a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6d043ddcafee3b2bfd1db05460cde8d6a86461a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 06b3b46c03f4832eb7f8c013aef32581b777e0f2.nq.gz
│   ├── 0ce0426386cc973499b961ad2644f8d353e83aeb.nq.gz
│   ├── 1470cd3dbf40b96a54cba2a84c4f10abae70a57b.nq.gz
│   ├── 1ba15f5af264b4e83a547cf8367a1b61c3905afa.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 585e92f8a32567537a46d216b3359e4da864b16d.nq.gz
│   ├── 58ba1b5861cd0ca2f4e0dc64e58ada868bf398ae.nq.gz
│   ├── 79e0d51bc0f8b6eade5b99f27b8a36351d0dd40b.nq.gz
│   ├── 8cf6735686e4b62b88fe41551ce13b3cc54a9b9d.nq.gz
│   ├── 9656ea858a4e410f72d7d8261f4968aae6fd8dcc.nq.gz
│   ├── ac7d9862d4238dd58300f8b85dea7491e3962353.nq.gz
│   ├── b974d7c5d71fad72409f266f98921043bc6773ec.nq.gz
│   ├── c08574e16d679b6d6ae5d2a8d2bc9432a2c27e01.nq.gz
│   └── e3def73628fee7848e5d63cd1a192b6a8f0e2c33.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6d043ddcafee3b2bfd1db05460cde8d6a86461a7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[datasette/datasette-litestream](https://github.com/datasette/datasette-litestream)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*

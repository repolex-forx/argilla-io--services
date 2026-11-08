# Repolex Knowledge Graph of argilla-io/services

RDF knowledge graph data for [argilla-io/services](https://github.com/argilla-io/services), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/services
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 16b0c95c73029bf8a53ea3d5eed09c5133fb06d1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 16b0c95c73029bf8a53ea3d5eed09c5133fb06d1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d20b6487c61e7d1bde93acf4a14b7a89083a16d.nq.gz
│   ├── 0d9e04b514860c5dc5d3eb3b48d28d1a65297bf9.nq.gz
│   ├── 15b5c4f5ec9c6498abf379b45fb9fa86b8c0496d.nq.gz
│   ├── 1f37939cf4ddd6d4a62d11d1f3867b2e588d2b89.nq.gz
│   ├── 2294e73dc229e1d1dcb35f57fff62b8bca877c35.nq.gz
│   ├── 2bd7bacb32c6c6d3109f885d5003491e138df094.nq.gz
│   ├── 4d2e6f5afb5e2bb608259ad44ac89a9078d93d5e.nq.gz
│   ├── 741d4a1f6ed6e7b71caa99c674a170d333f16b1c.nq.gz
│   ├── 75561d321136a5121c03190c9a8685bae599d089.nq.gz
│   ├── 9347530d069f7cb039fb7e6d5f556955934c7645.nq.gz
│   ├── 98265535edc13990336cb84b50a74ec2427057e6.nq.gz
│   ├── 9e584d389e63db7008f7c481686f8b01439796ce.nq.gz
│   ├── b2e0250120940f3bc3b8e75047e08de7a491c504.nq.gz
│   ├── c3548a12b4fb3748a99ee876a7d86a15bb0be04c.nq.gz
│   ├── e11502c4be1c994c2cdb86fefc7cf7d124069f47.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e7f72ee4ed54ba1c6a662fc5983206c76b14616b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 16b0c95c73029bf8a53ea3d5eed09c5133fb06d1.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[argilla-io/services](https://github.com/argilla-io/services)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*

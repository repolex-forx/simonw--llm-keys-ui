# Repolex Knowledge Graph of simonw/llm-keys-ui

RDF knowledge graph data for [simonw/llm-keys-ui](https://github.com/simonw/llm-keys-ui), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-keys-ui
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cb1dd2ff4962e8a8276da6ebc17169170f467c11
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cb1dd2ff4962e8a8276da6ebc17169170f467c11
│           └── chunk-001.nq.gz
├── blob
│   ├── 23d95820336e6e23f53461330d46b2336ca75794.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4dbaa6e7fb4c83ebe86e411b3477a365ddf8ae75.nq.gz
│   ├── 72203e17a9b87cfe68d06200f5ca8f328c451bfd.nq.gz
│   ├── 8433b121acb46137ab14ed4ad03d09dc3bbcbe5d.nq.gz
│   ├── 8c853af6d83c999b7e95de091fa67ab965ee0493.nq.gz
│   ├── 99289762b0f46c6c1340eeed16229bc6e04b37e4.nq.gz
│   └── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cb1dd2ff4962e8a8276da6ebc17169170f467c11.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[simonw/llm-keys-ui](https://github.com/simonw/llm-keys-ui)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*

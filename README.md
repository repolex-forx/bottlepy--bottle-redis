# Repolex Knowledge Graph of bottlepy/bottle-redis

RDF knowledge graph data for [bottlepy/bottle-redis](https://github.com/bottlepy/bottle-redis), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottle-redis
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4c2306e5c8dbaa271514bcc28980150b55d53f68
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4c2306e5c8dbaa271514bcc28980150b55d53f68
│           └── chunk-001.nq.gz
├── blob
│   ├── 0273b88a364b81cf623526fbf7735c46920f15bc.nq.gz
│   ├── 39092aabb182762e308802199e4b5cee5a9eb956.nq.gz
│   ├── 3b1571f769a730ac66b4bf9c60ce8299897bd805.nq.gz
│   ├── 5502228aafcd1e35411eaf244444a2eb935dee28.nq.gz
│   ├── 5e28dc925f75b2c2cdda9028e612a93badbe30e2.nq.gz
│   ├── 73d824f3aff5d1448521e03070c4e66b2a4724a5.nq.gz
│   ├── a8be0b7b9e5fc106305ef9b73f4ddfafb3cb5ad1.nq.gz
│   └── e57e3125f14335f971a7e970db5be2c8cf03e655.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4c2306e5c8dbaa271514bcc28980150b55d53f68.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[bottlepy/bottle-redis](https://github.com/bottlepy/bottle-redis)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*

# Repolex Knowledge Graph of napari/napari-console

RDF knowledge graph data for [napari/napari-console](https://github.com/napari/napari-console), parsed by [repolex](https://repolex.ai).

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
rlex download napari/napari-console
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 38503f8b2a7bc4a25290c813073c8be63cd3df2a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 38503f8b2a7bc4a25290c813073c8be63cd3df2a
│           └── chunk-001.nq.gz
├── blob
│   ├── 04393845e8d1e82a27ee78576655c13ad99a9c1b.nq.gz
│   ├── 1479be5f89d642bac43d0c038935a790ec7dc234.nq.gz
│   ├── 45759ebc527f43544d648bc7c8840f8c0e8d9a62.nq.gz
│   ├── 4fa93d0624c39b29ef082f0ef193632905bd1278.nq.gz
│   ├── 6531c65d9fc056e1c6908d5ad74eefffa050df76.nq.gz
│   ├── 7a5c90e8100c5a32f00419785af4a825e5bdad5c.nq.gz
│   ├── 8d3bcb3e5b55f7c1880fd1dfb10335273451b516.nq.gz
│   ├── 9f6285f404c55e755ca9038a7e2dea5aab59a70f.nq.gz
│   ├── b678ca5766523462462e13f468a49da8b641c425.nq.gz
│   ├── b74e8f9da35ef4a63c302c063ba4be3e2d6b871e.nq.gz
│   ├── b80a5db37b182ed752e623259aafff8bdb3409bb.nq.gz
│   ├── c6e54c1b1c01d1ceeaf1c7bbe3046ec3da1cb14c.nq.gz
│   ├── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f5be9e78567224f19c41f8be74626664dd8b446e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 38503f8b2a7bc4a25290c813073c8be63cd3df2a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[napari/napari-console](https://github.com/napari/napari-console)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*

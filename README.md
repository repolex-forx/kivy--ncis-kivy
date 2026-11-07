# Repolex Knowledge Graph of kivy/ncis-kivy

RDF knowledge graph data for [kivy/ncis-kivy](https://github.com/kivy/ncis-kivy), parsed by [repolex](https://repolex.ai).

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
rlex download kivy/ncis-kivy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b40a96ad00916a7a0d0ee8c49e476c79db908b54
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b40a96ad00916a7a0d0ee8c49e476c79db908b54
│           └── chunk-001.nq.gz
├── blob
│   ├── 05976aa6ea0373c02be48ee717a56b3cec3ea084.nq.gz
│   ├── 3fd282290e96c1d7e96e0fea6a6c605b63330d30.nq.gz
│   ├── 5a25821ae138f1cdf7531defcff73958555a036b.nq.gz
│   ├── 6fd2415116556fbc9b5b89d3f76107e6680af0c5.nq.gz
│   ├── 85a8f49b097aa292623ac2959a3a4082fe522172.nq.gz
│   ├── b1eecda5ef47c6c7ddf1dc608bcac0ff05bc6ac2.nq.gz
│   ├── bb86582c8fc8be733bc3b844be95ba52720e196d.nq.gz
│   ├── e3984f7f3c9bd403f2970d662984a4865e3bba2d.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b40a96ad00916a7a0d0ee8c49e476c79db908b54.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[kivy/ncis-kivy](https://github.com/kivy/ncis-kivy)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*

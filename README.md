# Repolex Knowledge Graph of alexcrichton/scoped-tls

RDF knowledge graph data for [alexcrichton/scoped-tls](https://github.com/alexcrichton/scoped-tls), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download alexcrichton/scoped-tls
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c0ff7bf6d33e568353ed863d90f893e7e80a0ed1
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c0ff7bf6d33e568353ed863d90f893e7e80a0ed1.nq.gz
│   └── repolex
│       └── c0ff7bf6d33e568353ed863d90f893e7e80a0ed1
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 36e6480e2c69260b3ad687f9a6ab14723ecbcc9a.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 6ef9917cf2d9da005d2a1f64f34937ac5df09890.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── d4567c2bcbd7ce1642b576d39340bea3d3e65732.nq.gz
│   └── fee6182bc5e8afd397a86e3bd48d67f0e859d1b2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c0ff7bf6d33e568353ed863d90f893e7e80a0ed1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 16 files
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

## Source repository

[alexcrichton/scoped-tls](https://github.com/alexcrichton/scoped-tls)

---
*Parsed on 2026-04-23 by [repolex](https://repolex.ai)*

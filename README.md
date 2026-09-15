# Repolex Knowledge Graph of jshttp/on-finished

RDF knowledge graph data for [jshttp/on-finished](https://github.com/jshttp/on-finished), parsed by [repolex](https://repolex.ai).

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
lexq download jshttp/on-finished
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1111fe8e913debaf3da9bd4f6bda216ef36097fa
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1111fe8e913debaf3da9bd4f6bda216ef36097fa.nq.gz
│   └── repolex
│       └── 1111fe8e913debaf3da9bd4f6bda216ef36097fa
│           └── chunk-001.nq.gz
├── blob
│   ├── 1917595a714e11049ec9402d87aa625c68caa080.nq.gz
│   ├── 207febba602fe63dfcf04cd5d2caa437cf35398d.nq.gz
│   ├── 5931fd23eab9dd3be559cd4bd81253df87a5297c.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 644cd814b9d745714e4d16753de8bc8856e201e4.nq.gz
│   ├── 6f2b43b2cc346bc3b18b5da67135d763f7c88da2.nq.gz
│   ├── 8973cded6589a6cc5a9e1718e3fb0d709fe6e8d8.nq.gz
│   ├── 9808c3b2b6602da61eb4afcb4caf33368e3e2bd4.nq.gz
│   ├── cf3015fb3b6ee818a7e76aff5854cde130fc5fe0.nq.gz
│   ├── e68df7bde39bb47aa1fd7eff4b317b3969de75bd.nq.gz
│   └── eaca44bd5025f6970036d1a1c3ebe94a9ed279fe.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 1111fe8e913debaf3da9bd4f6bda216ef36097fa.nq.gz
├── filetree
│   └── 1111fe8e913debaf3da9bd4f6bda216ef36097fa.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[jshttp/on-finished](https://github.com/jshttp/on-finished)

---
*Parsed on 2026-09-15 by [repolex](https://repolex.ai)*

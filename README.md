# Repolex Knowledge Graph of tkellen/js-matchdep

RDF knowledge graph data for [tkellen/js-matchdep](https://github.com/tkellen/js-matchdep), parsed by [repolex](https://repolex.ai).

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
lexq download tkellen/js-matchdep
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5d2e1bc61127ec6d0c95019a234daca40d2cb830
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5d2e1bc61127ec6d0c95019a234daca40d2cb830.nq.gz
│   └── repolex
│       └── 5d2e1bc61127ec6d0c95019a234daca40d2cb830
│           └── chunk-001.nq.gz
├── blob
│   ├── 03c0d754579284ea99beeb5af09067cfd4f12bb1.nq.gz
│   ├── 229016a3568ee54536d424b52eb29624ff0ad86f.nq.gz
│   ├── 2ccbe4656c6078ded72491cf2ee9c5ec20219624.nq.gz
│   ├── 2fa03a84189eae0d46b3777c742f048e90a04ea7.nq.gz
│   ├── 3b3d57f35c16c93a70002bf3e42ab88fd9b2cc3d.nq.gz
│   ├── 605bbb471d430801c008dd0e685152eca21fd58d.nq.gz
│   ├── 6abb72e1e92290c5acb68d1e92b4e22638804a67.nq.gz
│   ├── 8238c9f2c38a2c57b39f1265ecde6ea2e74743b0.nq.gz
│   ├── 85ab669558d128631695f63b0fca8b04d1363dd1.nq.gz
│   ├── 871895220b37a1e5081fed27e4d3b289be349c41.nq.gz
│   ├── 874a8ce56eb4e886c783359ea4709bdcbe520a12.nq.gz
│   ├── e30f600641a2852a5a614bd8b207e6b3bb39c6a2.nq.gz
│   └── efbdb9a9b7c31a75b0aed965b47c21bf62ddd7c1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5d2e1bc61127ec6d0c95019a234daca40d2cb830.nq.gz
├── filetree
│   └── 5d2e1bc61127ec6d0c95019a234daca40d2cb830.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[tkellen/js-matchdep](https://github.com/tkellen/js-matchdep)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*

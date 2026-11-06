# Repolex Knowledge Graph of sphinx-contrib/sphinxcontrib-run

RDF knowledge graph data for [sphinx-contrib/sphinxcontrib-run](https://github.com/sphinx-contrib/sphinxcontrib-run), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sphinxcontrib-run
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d6e0e5ceeabf39a02682b5c4b784e448bafef567
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d6e0e5ceeabf39a02682b5c4b784e448bafef567
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c693548224972c36e8ddffc5aad4b39d058c598.nq.gz
│   ├── 0e0298603a7fb228e310375533be9134fb4e6da0.nq.gz
│   ├── 0ec69a2a9261da7185620236fa80f7ce18f90bbe.nq.gz
│   ├── 19723023235bb7da695e68edf34c0d2d2ffd4d8e.nq.gz
│   ├── 329945de8cb824eb098eb6d7a58c7f5e443871d8.nq.gz
│   ├── 5f62d6d546315ad0f92858af663d7af66a80b0e0.nq.gz
│   ├── 66ce5feaa9b7e65e509742269fff4697ccab28d1.nq.gz
│   ├── 802741b4cc96cb9f0366ebe741fa6b876fab40f6.nq.gz
│   ├── 99c5f6f7d8756aaea9f400c85e35a26a5f4374e0.nq.gz
│   ├── 9d25048c3933ca188a7ce0abbbd406f62fab88da.nq.gz
│   ├── cd53caf4456c3ac531168d3ef102741496704e70.nq.gz
│   ├── f6c9be4bffcc2a0e31c40cc50a0a478981efb4e8.nq.gz
│   └── f8d736b1b9cd4bd8b93e694de30e88ae42aa97bb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d6e0e5ceeabf39a02682b5c4b784e448bafef567.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 19 files
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

[sphinx-contrib/sphinxcontrib-run](https://github.com/sphinx-contrib/sphinxcontrib-run)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*

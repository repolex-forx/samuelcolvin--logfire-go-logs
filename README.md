# Repolex Knowledge Graph of samuelcolvin/logfire-go-logs

RDF knowledge graph data for [samuelcolvin/logfire-go-logs](https://github.com/samuelcolvin/logfire-go-logs), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/logfire-go-logs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8b3eba6d2f5fa9e345e080358590078797f6db78
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8b3eba6d2f5fa9e345e080358590078797f6db78
│           └── chunk-001.nq.gz
├── blob
│   ├── 16ae11560c693d4386241c341d3a329de532b748.nq.gz
│   ├── 32e03e427af5386002b60c10e3db3ec62c9e9c80.nq.gz
│   ├── 5c2d8056ca0acfa7e04e9c0638b621b6de3e0c92.nq.gz
│   ├── c778973688158cb76eb5cedeee957f0662f11174.nq.gz
│   ├── d6a371eec334d8f413d16d296ae054cb90c3fe7d.nq.gz
│   └── e6207f526a03af19d81159deb871e913aded11e8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8b3eba6d2f5fa9e345e080358590078797f6db78.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[samuelcolvin/logfire-go-logs](https://github.com/samuelcolvin/logfire-go-logs)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*

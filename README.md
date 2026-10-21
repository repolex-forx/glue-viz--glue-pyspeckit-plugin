# Repolex Knowledge Graph of glue-viz/glue-pyspeckit-plugin

RDF knowledge graph data for [glue-viz/glue-pyspeckit-plugin](https://github.com/glue-viz/glue-pyspeckit-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-pyspeckit-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cf28d9e504ab95baa2f0db10abbc1971dc641250
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cf28d9e504ab95baa2f0db10abbc1971dc641250
│           └── chunk-001.nq.gz
├── blob
│   ├── 078018f66f89413d99b5a720d26800e5f6d94f4e.nq.gz
│   ├── 07f710935ec3c8e9d048042ef387cecb66c26e44.nq.gz
│   ├── 253eb77282c7f1e8e5089b1166c154bcf5c4845d.nq.gz
│   ├── 402f86e9b58b0c2fc673ecf6362700cc9469019b.nq.gz
│   ├── 5e1dfc4391518fdc90f6191c4ff8ce3b81c7c1d8.nq.gz
│   ├── 774c27955c31e1bb148af899146f48e1449255e6.nq.gz
│   ├── 82feafa2b552e1b5bec6d6a5e8bc3c98ff0f71e0.nq.gz
│   ├── b28d0543191eba52daeb06803c2f2bc734d04986.nq.gz
│   ├── c90f84ee8c74c4df0f46771b63c048af44b8fbb1.nq.gz
│   └── e783b48eb8fe930f185773b1398dae9caa9235fb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cf28d9e504ab95baa2f0db10abbc1971dc641250.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[glue-viz/glue-pyspeckit-plugin](https://github.com/glue-viz/glue-pyspeckit-plugin)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*

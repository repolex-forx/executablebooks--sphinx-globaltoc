# Repolex Knowledge Graph of executablebooks/sphinx-globaltoc

RDF knowledge graph data for [executablebooks/sphinx-globaltoc](https://github.com/executablebooks/sphinx-globaltoc), parsed by [repolex](https://repolex.ai).

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
rlex download executablebooks/sphinx-globaltoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ea6c5ad08c125d1d8a3ec87ac34440cb2669e445
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ea6c5ad08c125d1d8a3ec87ac34440cb2669e445
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a5821aa5cddc58d43087f72eb2c36984b2d9fcf.nq.gz
│   ├── 0e40ab512b575da991a06e059f39eed997c1b5d4.nq.gz
│   ├── 37df5318449c7170de241548d5dad8c2d8cd969e.nq.gz
│   ├── 4322bb22f9d4fa454d0a1345201b05e9246c5169.nq.gz
│   ├── 45456bc7643b3e76b40ff377e9da0de9cb04428a.nq.gz
│   ├── 48efe1faf97eb9ca637e75613bf14a8e62fd617b.nq.gz
│   ├── 4b9ab124002bf6bdde1b83eefc13b5fea4f2cc75.nq.gz
│   ├── 530eb5a586857418c899768e409cce133cf46fd2.nq.gz
│   ├── 675af3b1ccb96d0cb414854bc8e6eefb78cd3091.nq.gz
│   ├── 6fe927da2f1bf15e2da20864454ff8d8f0380b9c.nq.gz
│   ├── 81b3975784494d530b446294d2a0610c77eaf003.nq.gz
│   ├── 99294eaee06cda4dfdd472aef6108b0bfa99f03f.nq.gz
│   ├── 9d43d77dc73c255f3747b3c0823c38ec6df53c78.nq.gz
│   ├── b5541dcf033e544b4d5eab71b798c093b29239da.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── d127d153eaa9bdb0d3f8cb33ac260fc5e8f6e09b.nq.gz
│   ├── dab6ba48f3dcb26eae65920afb84113b1ebb141f.nq.gz
│   └── e0074aa34e987476a214065f5532b302f0613e6f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ea6c5ad08c125d1d8a3ec87ac34440cb2669e445.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[executablebooks/sphinx-globaltoc](https://github.com/executablebooks/sphinx-globaltoc)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*

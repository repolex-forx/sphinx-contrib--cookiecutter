# Repolex Knowledge Graph of sphinx-contrib/cookiecutter

RDF knowledge graph data for [sphinx-contrib/cookiecutter](https://github.com/sphinx-contrib/cookiecutter), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/cookiecutter
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── aa221237cf02f0d838a08abfcae894656acdaf3d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── aa221237cf02f0d838a08abfcae894656acdaf3d
│           └── chunk-001.nq.gz
├── blob
│   ├── 15f8793a7eef7e5ec7c999dfe32fda014903d0cd.nq.gz
│   ├── 1d45dc6ea30fb622e1c50396757105770b0b9685.nq.gz
│   ├── 23226a5ab6dda31de5ab811be9f9b9e9a7bd802d.nq.gz
│   ├── 46e25ece07c47557027f9e3cf4cf04ebd8c20610.nq.gz
│   ├── 4ccdbfc7224f7e10e80121472173d201f09edfe2.nq.gz
│   ├── 55ff9de50d6ca483766e6c2f6c04990de5eb12df.nq.gz
│   ├── 5834978c15df90f7f1bc63192ec6bf1b7fec3cae.nq.gz
│   ├── 5acb1a6f03c8ac270d377335465dc8c0e17d4110.nq.gz
│   ├── 6242492c810f9795c07b5c57a60ef26c48edbec5.nq.gz
│   ├── 815a482748a6f00035a0ebb7643aba272445427b.nq.gz
│   ├── 96d00f17a46282e347e25402af3789a48b785a8a.nq.gz
│   ├── ac7d049af032e3844752d27d07bb59fa97ab4907.nq.gz
│   ├── ae0f862b865ef2f17cee6a962d8fb480d7229488.nq.gz
│   ├── b7402c179523f908cd8353fc760030d7dc20a975.nq.gz
│   ├── e1095ce6e088a91932b1fab6e53a0f1801a767e1.nq.gz
│   ├── ed8810e716c7cb115be3eabdd508fa382d146f0a.nq.gz
│   ├── f7fce8751c7cf5519b1dcbeff315939f47ea406f.nq.gz
│   └── fe28f4b545c2a4159f6cdb5543a6f162aa8316f8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── aa221237cf02f0d838a08abfcae894656acdaf3d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[sphinx-contrib/cookiecutter](https://github.com/sphinx-contrib/cookiecutter)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*

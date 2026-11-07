# Repolex Knowledge Graph of beeware/duvet

RDF knowledge graph data for [beeware/duvet](https://github.com/beeware/duvet), parsed by [repolex](https://repolex.ai).

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
rlex download beeware/duvet
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b2058f36235425cbd4e7faf430d20d250cd7454b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b2058f36235425cbd4e7faf430d20d250cd7454b
│           └── chunk-001.nq.gz
├── blob
│   ├── 09e27813f8a570d253cc3221869a5946775e9eab.nq.gz
│   ├── 216107e99c72db0dd8fe55c77b83101892d3557d.nq.gz
│   ├── 3d4a5f9bc987088d2654a8a47642022d419df940.nq.gz
│   ├── 40ad611f22b1153999c60e4433e899a037e5f7e6.nq.gz
│   ├── 43c1f4f1d48498890ea1df173810e6272b284ed5.nq.gz
│   ├── 442aafa13dc8614c58a61ffcb98bc65fe592162c.nq.gz
│   ├── 4ce5c3fdf8684039c14ea0707f74181373dd5a71.nq.gz
│   ├── 550e031f08629c2b1c6c46a0274faf75be235a72.nq.gz
│   ├── 63515bae64b0452bf5702d3f649912b57939f16f.nq.gz
│   ├── 684bddb351554ce6648aa58828e0ee165b38dfa7.nq.gz
│   ├── 785768626bd2b454ad2b2351190b93c3e79ff768.nq.gz
│   ├── 78b1aa221af323a76c0976c9e132b51ee431f31e.nq.gz
│   ├── 832d2a571fc1655cae0634859d455099cf29e4ba.nq.gz
│   ├── 985ff2ba1d7524275c10698e4ffed20322863605.nq.gz
│   ├── a418fed521b7b915707d6838011c01358a107c82.nq.gz
│   ├── cc23e426c6f87b34a44b4dc34a1aca8f88e8bd51.nq.gz
│   ├── cfad5d249e8c99302455ed4ae5279bea6e827683.nq.gz
│   ├── cfc94c922170858fa0aeffd1900b55bd5c1573b7.nq.gz
│   ├── df93f7499d8578a0b3f215973149d255c1cba005.nq.gz
│   ├── e423827f5b486cc5fd71bca6ab2a8091235f75ac.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e96fdf1674e28ccfc3c8fcb3800b9e8e07db342d.nq.gz
│   ├── f824c918802c6ce201c3c105e1505336be855b80.nq.gz
│   └── ffd18458258af3f40acbab23358e64c1d732cf65.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b2058f36235425cbd4e7faf430d20d250cd7454b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[beeware/duvet](https://github.com/beeware/duvet)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*

# Repolex Knowledge Graph of BurntSushi/termcolor

RDF knowledge graph data for [BurntSushi/termcolor](https://github.com/BurntSushi/termcolor), parsed by [repolex](https://repolex.ai).

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
rlex download BurntSushi/termcolor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 224c903a46a7204dea5beaa1120491a286255e29
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 224c903a46a7204dea5beaa1120491a286255e29.nq.gz
│   └── repolex
│       └── 224c903a46a7204dea5beaa1120491a286255e29
│           └── chunk-001.nq.gz
├── blob
│   ├── 097a4da7f1ef2d145d2f9488f541fbb3d9776fc5.nq.gz
│   ├── 2115d1275b141020f62537bbff2c9d8104269035.nq.gz
│   ├── 2f2825f4e7870ded4ec817373f903f9cab406ea2.nq.gz
│   ├── 3b0a5dc09c1e16357459ddc9182a50f360f3cdba.nq.gz
│   ├── 4720b6256117f2a6dfce3a1feaf86bc72c03d237.nq.gz
│   ├── 58dbbb6ef1ec25ac03f922c4fda266fef6ef5179.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── a196efbeb43dc6ee66a1aa4c89bede3172e393f1.nq.gz
│   ├── b4e2c7f00663dbeb138f756cdf20c1363210f0cd.nq.gz
│   ├── bb9c20a094e41b7632d63bcff20c0b4b95e80777.nq.gz
│   ├── cc780340e18431f4780372768a5a462aa89fc9cd.nq.gz
│   ├── e54d2838c76792dbaabffee9aec83cf9fe7c2756.nq.gz
│   ├── f220b592f7126d93010e19304f6b5719f93e2db7.nq.gz
│   └── faf3edb2daf58d98f9365bc49b50826a5557f6f2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 224c903a46a7204dea5beaa1120491a286255e29.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 23 files
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

[BurntSushi/termcolor](https://github.com/BurntSushi/termcolor)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*

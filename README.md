# Repolex Knowledge Graph of huggingface/trl-jobs

RDF knowledge graph data for [huggingface/trl-jobs](https://github.com/huggingface/trl-jobs), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/trl-jobs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 07d3ebec301c89ea520124bf8643117104e0e532
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 07d3ebec301c89ea520124bf8643117104e0e532
│           └── chunk-001.nq.gz
├── blob
│   ├── 074f86afcc8e2bdf32bfb96c4866bd88c91b3eeb.nq.gz
│   ├── 08ad4ecd66833ea26d2201c7897f156288407b6b.nq.gz
│   ├── 120eabbe9a7cbb151eb4c51cca9f5a8f4a6e172d.nq.gz
│   ├── 1ce844a5c54e314628e5b2c46857091a652897cf.nq.gz
│   ├── 35c471a8091dbdcbb4cc2575706af2d3592b5724.nq.gz
│   ├── 377bef536ccb9c6d544877887296f51763a0c7b5.nq.gz
│   ├── 3dedd334a94b79521b9d66aa5b3824b456990642.nq.gz
│   ├── 3e95b719050df0be96da5d3a8bc40c769328777b.nq.gz
│   ├── 4f6c777d5f5954bffc8acb33bbf346b5d5e10b0a.nq.gz
│   ├── 592def2831f3b5786a6b7a2636cf34398cd359fe.nq.gz
│   ├── 60a2d3e96c80e344efb192a6536f018f6deef60a.nq.gz
│   ├── 79d1eafee13631ce6f4c9f2c63a4ec4eafc8e15f.nq.gz
│   ├── 82a91e874b0fd5b96dca4dc5c934b95a08cddec6.nq.gz
│   ├── 8c70153e7ecdab78b58bd5924f3bd57ad27045a9.nq.gz
│   ├── 9a368cd2c657928812ea4a3dfa8b8940f96742f9.nq.gz
│   ├── a28863de8774781b3935106f3271bcb4ec200199.nq.gz
│   ├── a43702403563e4468898c1e44fc7f7648930b22e.nq.gz
│   ├── b6c1b1ae46d687d4b333b1d9d8a0414de0ecc476.nq.gz
│   ├── c70d5235b3b7cce44feff60d7c4c754ed148a850.nq.gz
│   ├── d5feac76bd289e3a8f35360ff43e436f3c7aacbc.nq.gz
│   ├── e564cc88a9e0554bec80cebcb8472bb2ebd4120a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebc1aa0ed7831fa62beff2f5bd3a1c1632c21bf3.nq.gz
│   ├── ee738de89c02edb2ce1ae2bd31d2c7163d0b3af6.nq.gz
│   ├── f1de51824573c6238968f45805b6d2b51512cb09.nq.gz
│   ├── f70817b113e358e7fa96cde5b929e30b61e9acfc.nq.gz
│   └── fffa213b9594754ffe87f6158ad84320b3a17fad.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 07d3ebec301c89ea520124bf8643117104e0e532.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 34 files
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

[huggingface/trl-jobs](https://github.com/huggingface/trl-jobs)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*

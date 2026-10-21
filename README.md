# Repolex Knowledge Graph of scverse/stats

RDF knowledge graph data for [scverse/stats](https://github.com/scverse/stats), parsed by [repolex](https://repolex.ai).

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
rlex download scverse/stats
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c0a555b6239ddd4f456ba3f02202569b2215a539
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c0a555b6239ddd4f456ba3f02202569b2215a539
│           └── chunk-001.nq.gz
├── blob
│   ├── 0933b226b5816edd804431262a76aa4af8438843.nq.gz
│   ├── 0dba20947e3cccf3ec8fc876746ec1e3a7cbeae7.nq.gz
│   ├── 0f3e1766a18d4d62c36ab7366cf175c94cfe906d.nq.gz
│   ├── 1a2f5bd2045147ae9638adf9a51971e031542b0c.nq.gz
│   ├── 1c75975d5da185e27af5ef169d0502191a49be1f.nq.gz
│   ├── 44dd0f4ab890eb540ab136a2d515db2f0821dd40.nq.gz
│   ├── 49f1ff06173a1159b09b2b2ed086167880da0fb0.nq.gz
│   ├── 5356963cde646e80ac9b1bf169ce313d9b1e30f5.nq.gz
│   ├── 56a6b9bb00365a803fecd808897163d7d8e4ccfa.nq.gz
│   ├── 5b07329d920da7e002bba82c508f8ea74d3d1c07.nq.gz
│   ├── 6e2b7e92e695421b9568ddb320c84e041fc4a9f7.nq.gz
│   ├── 71fa0b72bb0689b044689d91a4d239e44addd303.nq.gz
│   ├── 785d6b2ae637d2dc4e60ff6ce3b2980d43b401d5.nq.gz
│   ├── 83419361c5815027c30acd54c84e6f0abb59ba49.nq.gz
│   ├── 923c6880ee7eb3c240c1d394195cefb8abfee4a3.nq.gz
│   ├── a6161e259f1dfd4170fc19ca51852aeb69bd20b4.nq.gz
│   ├── b9f8e9c1eb91a774655498e29bfc473619eef0fc.nq.gz
│   ├── c993ed74683af3a7d0d399fe2fad9650fa84715d.nq.gz
│   ├── cbd4903a92cb90048c7483d3fa47d0a8626f515d.nq.gz
│   ├── d81f29aac43a15fbafb6b245ebdfb9eab7e14db3.nq.gz
│   ├── d86bf45bbaa6a41b3665224c614f5dcf0ee30429.nq.gz
│   ├── e6297f4ed393276d3a15809fdc95ef1c4da5f237.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e6a94b1a8e91356704679fde2b0860c539781e15.nq.gz
│   ├── f1098e4e4d717498e92d4cd18e5a9cc1cfe78947.nq.gz
│   └── f2c1619b82ba29402a7b0bc0e6af50fc4272c2a5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c0a555b6239ddd4f456ba3f02202569b2215a539.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[scverse/stats](https://github.com/scverse/stats)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*

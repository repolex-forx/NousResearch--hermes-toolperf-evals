# Repolex Knowledge Graph of NousResearch/hermes-toolperf-evals

RDF knowledge graph data for [NousResearch/hermes-toolperf-evals](https://github.com/NousResearch/hermes-toolperf-evals), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-toolperf-evals
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4e13ec24fafe94f48c9d96f4bdadb6b5577ebc02
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4e13ec24fafe94f48c9d96f4bdadb6b5577ebc02
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f8525eaacf40cb7da6420362705eaa0c3443059.nq.gz
│   ├── 176685ecd316f213342509696e61227a36db5c4c.nq.gz
│   ├── 22dfd87fc054fb758c6d8483a80a6aed7ba151a2.nq.gz
│   ├── 470ff9feb0209d3e772e41c312ffa93e474c18c8.nq.gz
│   ├── 64447e108a1ed56e4a6f11e624ee93191d636460.nq.gz
│   ├── 76d2676837809e59db3d066e49d93f9869730f84.nq.gz
│   ├── 7dbb94d427f8c39304b24eab03dbda98e537a68e.nq.gz
│   ├── 82e9adf2ed9e9a3bfb834c9219b92f0b24abe872.nq.gz
│   ├── b5ca6a161d122ec0f510c7b3c5748ae30e834301.nq.gz
│   ├── bcb195c9647848899439b9c39bc2cc5a12bac1cd.nq.gz
│   ├── be96e22fdffd6d5a0b08e937839474b05921885b.nq.gz
│   ├── d01b27581db64d62adcaf976e402f5965ecf2c99.nq.gz
│   ├── d39daa66ef6bd04317aa390ff71b752dd9a57963.nq.gz
│   ├── dde9ccbac5ef35c8f2cf604fa6c1f8c6a1a0044f.nq.gz
│   ├── f18dfd5fd1bc8c5b5e291971a4a37037f5804534.nq.gz
│   ├── f53e255a230dac5ed5d4649727aa788a4c72165f.nq.gz
│   └── fd4f8e5cf502b3296e92b94e18672518372b0c9d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4e13ec24fafe94f48c9d96f4bdadb6b5577ebc02.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[NousResearch/hermes-toolperf-evals](https://github.com/NousResearch/hermes-toolperf-evals)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*

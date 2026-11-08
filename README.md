# Repolex Knowledge Graph of zenml-io/zenml-agentic-workshop

RDF knowledge graph data for [zenml-io/zenml-agentic-workshop](https://github.com/zenml-io/zenml-agentic-workshop), parsed by [repolex](https://repolex.ai).

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
rlex download zenml-io/zenml-agentic-workshop
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 259ed0154f05123268be07a9f3618d62d87e75b9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 259ed0154f05123268be07a9f3618d62d87e75b9
│           └── chunk-001.nq.gz
├── blob
│   ├── 110c3e775272c71efa8ff4c991cc350029ee239c.nq.gz
│   ├── 2de0eb30b87b64d0539eb8c2a236d3728aad7ecc.nq.gz
│   ├── 342a3674f620ff19e6eba43f645c3c27275f2618.nq.gz
│   ├── 35b91966d44912affdef8d1d4919dde2b0ffbd29.nq.gz
│   ├── 382dfbe491b8ad98798f313c9c6adc0f3174a40f.nq.gz
│   ├── 4e435d2702feb8a4638c8759b5d161f0ab1da2d0.nq.gz
│   ├── 4f108e281f9a5d89f00cfcbb4a8534ac5f196ee4.nq.gz
│   ├── 64e6e17db3505be53b6aa98ee1297487e36ce45e.nq.gz
│   ├── 6dabac1e578d3425e558680c10159a22cc889ee1.nq.gz
│   ├── 7ab8108ed8e5d24c3fd53cc780e93feb64945ec3.nq.gz
│   ├── a43551e5da833891cd958ee1832c4477e5f28173.nq.gz
│   ├── ae410d2568dc7884ebe0f94d27b12d44c3e59755.nq.gz
│   ├── ae867761266ed2d6201c760324ee59782748df9d.nq.gz
│   ├── b571825c5d1bffb03a62129b858d21c874893829.nq.gz
│   ├── c0329ba2be860539b63f8f321e9c646b7362ee9c.nq.gz
│   ├── c26e5e2c6b1539721d72fd94ee10d5d724cc7dcc.nq.gz
│   ├── cda8001f8d39dc9e4e6fef492a5a2fa133377162.nq.gz
│   ├── e80c1ef375f1d6b882a57956ffb3cdac2209de9e.nq.gz
│   ├── e9ca1107f5533b2ccb203b368026a0e96a041596.nq.gz
│   ├── fd4574031cbf62a00a15f6d09bdb2649df8b7ab5.nq.gz
│   └── fd99658436dee2ebc98f46a1049f040c0727e7ff.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 259ed0154f05123268be07a9f3618d62d87e75b9.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 27 files
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

[zenml-io/zenml-agentic-workshop](https://github.com/zenml-io/zenml-agentic-workshop)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*

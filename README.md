# Repolex Knowledge Graph of redis/hiredis-py

RDF knowledge graph data for [redis/hiredis-py](https://github.com/redis/hiredis-py), parsed by [repolex](https://repolex.ai).

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
rlex download redis/hiredis-py
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3cb8f069006f7138620b065fba973ccc490bde3d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 3cb8f069006f7138620b065fba973ccc490bde3d.nq.gz
│   └── repolex
│       └── 3cb8f069006f7138620b065fba973ccc490bde3d
│           └── chunk-001.nq.gz
├── blob
│   ├── 08aedd7e61b9921f0a7844c3826bda5c611bc5e2.nq.gz
│   ├── 0cd4acde1645f91d5f9c36f31dbec341acedfd7a.nq.gz
│   ├── 209b6b73795ab371b6126de3b7a3c379f9a8d6c6.nq.gz
│   ├── 23e4004d18b0d7fb6cb9d9dec9bef8f51acb4b97.nq.gz
│   ├── 2c3dbfd08d9d4fb545f3fdac733159c7519d58f9.nq.gz
│   ├── 3bda847498e0c41d543103407b3e576269c62022.nq.gz
│   ├── 49cebce7e6a654e66af48e5087b1d805f007be48.nq.gz
│   ├── 5194e610722a8ad8032cb27347e6f516c503291d.nq.gz
│   ├── 5d6652e62e160208f705134ef578f05a7ec5d01b.nq.gz
│   ├── 6055335e06b61ceb34ab54fa754d228f6d23c2bb.nq.gz
│   ├── 6729c1b9e822e6fe7918cf9f3e5819a018f89400.nq.gz
│   ├── 6a12f117e4b25ff970f11455643e3c47d56849a5.nq.gz
│   ├── 71f4188f415787df71b8b3bc3f8a5cc58400d84e.nq.gz
│   ├── 77e84ce5b121d62884ef2a7de0123cc5ba06b915.nq.gz
│   ├── 7a3fc559c20de2c75d2a1098e18b2284403ddf80.nq.gz
│   ├── 7af82c03f9991dbb4480767748a9f2c4269bf5fe.nq.gz
│   ├── 862c517e10a24de84fc218a0ce376cfe82c10012.nq.gz
│   ├── 950193be54c3831c4a4d9060d9325b61772232f7.nq.gz
│   ├── 9ccb28aca4880fccf757b9559bd85706be789099.nq.gz
│   ├── a0b3dfefedfd2062b596eff71ca2a394c6e44900.nq.gz
│   ├── a0eff07a9ff1b6f09c08285b4b8a13daca0218d5.nq.gz
│   ├── b1bcdc35739998b3916652188872cc34d99540a3.nq.gz
│   ├── b22748ebd28cde808ac2bf2f7f912436d3016e72.nq.gz
│   ├── b8ca6cca6fee3feebdc22ebccf1c42ab25996227.nq.gz
│   ├── baa722d753150d054157b0c246ae251001956157.nq.gz
│   ├── c9359c19b9db6eaf072004ee386b1734c463690a.nq.gz
│   ├── cbe3746e18f816ef8111f04d538e20ef168e09f9.nq.gz
│   ├── d072021dfcf41d2252fa9c2eb723ecbd7d6e2e9b.nq.gz
│   ├── de2d4862208b469662ecb9ba08d040018ee8b06c.nq.gz
│   ├── e15284155333e46d5dceb9ad365624a892814aca.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7d852ebda008b1a13f90f4be44a4118853dcfc7.nq.gz
│   ├── f8580728d1cd16d48c85271c1767aa9b8213860f.nq.gz
│   ├── f9d58a024d4b7c01741bad2c6e061d5943b6832c.nq.gz
│   ├── faa354b485a6fde2d09b2f3732c04e288d0af1b2.nq.gz
│   ├── fb645d00dd7b8b980506c3752f6113547c640ba5.nq.gz
│   └── ff0416876a5c2679aa45fe15b87126bd8a14a40a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 3cb8f069006f7138620b065fba973ccc490bde3d.nq.gz
├── filetree
│   └── 3cb8f069006f7138620b065fba973ccc490bde3d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 47 files
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

[redis/hiredis-py](https://github.com/redis/hiredis-py)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*

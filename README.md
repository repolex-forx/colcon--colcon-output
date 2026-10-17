# Repolex Knowledge Graph of colcon/colcon-output

RDF knowledge graph data for [colcon/colcon-output](https://github.com/colcon/colcon-output), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-output
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7f44232dc5bc3a116f3347c5e49192a93ad64159
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7f44232dc5bc3a116f3347c5e49192a93ad64159
│           └── chunk-001.nq.gz
├── blob
│   ├── 018d79172c5fb6c50b2e7ad0bab184532104a803.nq.gz
│   ├── 0cb9028831f797a2d498af1cda1982c36dd4543d.nq.gz
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 1370bd50e784e95adc76325b471a7e681ed709bb.nq.gz
│   ├── 25bb908495379936a8497e7c9ab62cac753a21b9.nq.gz
│   ├── 4deba61b1fa40b1290bd1870d4d816b409d68e67.nq.gz
│   ├── 51c8831c17fae3474ac109473c55d2162c5b3bbf.nq.gz
│   ├── 56590a354cea18857708c4903384b2cddf9987a3.nq.gz
│   ├── 5960d844afbc7be7925e61ee6f6308dfda30ab5e.nq.gz
│   ├── 656165e701d3e7986d4c7c56e9c81a9837a6efaf.nq.gz
│   ├── 705847dec085fd7a94c6ec259afefbbf7064a0fa.nq.gz
│   ├── 7c86db2550adddd70d9a77b6ba7a9571b8d50264.nq.gz
│   ├── 8d315d51e4f6e4f533a08823b5cc3627e9540cc2.nq.gz
│   ├── a3af3fb9d87d70f03f8164306cd92ef5fca48198.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── cf77acc13d1941a1e28359479101a09fcc4a45e5.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d8d5957ce4996d6c2a0fb3a2aee5f3a34bed9c53.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7f44232dc5bc3a116f3347c5e49192a93ad64159.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[colcon/colcon-output](https://github.com/colcon/colcon-output)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*

# Repolex Knowledge Graph of plotly/dash-slicer

RDF knowledge graph data for [plotly/dash-slicer](https://github.com/plotly/dash-slicer), parsed by [repolex](https://repolex.ai).

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
rlex download plotly/dash-slicer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b1223dcd29fc7523d5fe3efec02fd849518a603
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4b1223dcd29fc7523d5fe3efec02fd849518a603
│           └── chunk-001.nq.gz
├── blob
│   ├── 05d91c588b887f2f4defffe2f3afb89488f31bcb.nq.gz
│   ├── 08fe1e8fd559b124dde041434c4ccba7e69e9ac9.nq.gz
│   ├── 0aef203a8ccc4a372fc1abbba766ff2ef7987198.nq.gz
│   ├── 13999b67bae28f2228de44396c9901631acb2d55.nq.gz
│   ├── 16c2ee31d3ffd207288c829a739f1f55db1459ae.nq.gz
│   ├── 193f6a2f4d560ae4c7cb920f4e57b68922d31469.nq.gz
│   ├── 1f2ea260b0c722684ee9a6793fcceeacb7d9b078.nq.gz
│   ├── 1f34e0bbf2dea4e1f774c9848a9e11a832372731.nq.gz
│   ├── 2303c72d20215b973cc34df8eeeb5e1261b69a1c.nq.gz
│   ├── 32e65044ab51d6cea864905dfde5bb5b28fdda4d.nq.gz
│   ├── 39e30a6cbf86513c695e732bdd10e62d46552dd4.nq.gz
│   ├── 47e439f26c9733957cba0e883e36594c2624971d.nq.gz
│   ├── 518a36aa78681b760a25d7bd4b98e1009b9b9360.nq.gz
│   ├── 5c0460bd7c78ac90858f929c2c33e53f7f3d748f.nq.gz
│   ├── 64ba684fa57bfa21a143fbd44dabd570dbf66bad.nq.gz
│   ├── 6aaa21f1796100b3e87d96c412e968cfec9316b7.nq.gz
│   ├── 6dbdee2c8106dc95396dd895cb3c2dcf6a320b60.nq.gz
│   ├── 7f4a9fa448c513689538e09b2c93082d89298e28.nq.gz
│   ├── 807695ddc5438e7351b3383034ad73530c7e3422.nq.gz
│   ├── 81db7cbdc352e25295e2e85d3223df7671e696d2.nq.gz
│   ├── 924da31a52e0a4ea5f865a8385c28b1215fb274d.nq.gz
│   ├── 9b7cafcdbefc17d5c87cfc7df4492ec281bc30d6.nq.gz
│   ├── a164f8e23d8ef11813846fe2fc5006003cc587fe.nq.gz
│   ├── a8a33a4ab7d767834b8e5d2a2dc8f8eb8cebd01b.nq.gz
│   ├── b1eebc04e7c5c237cee920ddc2656b76b1fe206f.nq.gz
│   ├── bc8371522911dae5c57fa15028a9c84eeb316709.nq.gz
│   ├── bf16a2b7d27f4cc5384c9e4c63a797a54f2c1713.nq.gz
│   ├── c65dbee039ad2f6367725eefe42ab12464f67002.nq.gz
│   ├── d2d900a1140c7905abde8233ced3e087fd2bd7a7.nq.gz
│   ├── dc5be6031060617a52087b31f907f64c93850ef7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e885befe18345ff40f43516196be027b0e41c8c4.nq.gz
│   ├── eb1b94d952c89eaeff248f86efc93c142be5ac21.nq.gz
│   ├── ee1a9e5f2cc54ba7b0c41c6ed94300538e1e6af3.nq.gz
│   ├── ef7f0954d07fc6f21745f26f768545d7674c9bf9.nq.gz
│   └── fc1757eee8e14cea893ce494b8510166be5170c6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b1223dcd29fc7523d5fe3efec02fd849518a603.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[plotly/dash-slicer](https://github.com/plotly/dash-slicer)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*

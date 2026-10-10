# Repolex Knowledge Graph of pypa/dependency-groups

RDF knowledge graph data for [pypa/dependency-groups](https://github.com/pypa/dependency-groups), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/dependency-groups
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── facfeaf7f8424c35301e218f6e9269a284c9421b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── facfeaf7f8424c35301e218f6e9269a284c9421b
│           └── chunk-001.nq.gz
├── blob
│   ├── 0113fab2dea05d5074cedd31722b9c3b02fa5280.nq.gz
│   ├── 06c9b412ef02f902594477ba5c2ff2d80f654218.nq.gz
│   ├── 1eca7f22d6da6869d6126d5313ae946a277099a2.nq.gz
│   ├── 2390d8c809eea1d6587357cdad25ed4af134db32.nq.gz
│   ├── 248b4c9a04c9b735a174c649d4ff1bc7dc336ab3.nq.gz
│   ├── 26e06565de98da60a3259754fd37ca25e44eade5.nq.gz
│   ├── 2a8f71bc2ae4960525756d267c90912ddc7994b7.nq.gz
│   ├── 4293cc9aed9fab9cfbbfa5b8cb950387c78d40e9.nq.gz
│   ├── 4740638630323d06ecfdbcfd6a939925a18ffcc9.nq.gz
│   ├── 484ba420c8356d4a2adf0d3cedc89dc21fa3a42a.nq.gz
│   ├── 55b1efce72b0fadd5a0281a33d096fc2f4267097.nq.gz
│   ├── 6307be9127a79912450576f92a177948503c8754.nq.gz
│   ├── 670d4cabe5c860d61e03b2677d68f38b07e93870.nq.gz
│   ├── 69d3accce17edca786ac4fb5e2e28b17abf5122d.nq.gz
│   ├── 70a6fd68b904c9aeed8f4ed6748196e8732b5d49.nq.gz
│   ├── 804f7d278454d26a54f5c2635aebd3365bf5e8dd.nq.gz
│   ├── 81c8765c62d7431c5f69fb759adce617a443bb5a.nq.gz
│   ├── 83e44d81b715fb2693b38b806fb9f4bb58c8a54d.nq.gz
│   ├── 9444e92a94d24cfc9ccf517648952ae4d4090e03.nq.gz
│   ├── 9605b71308cd78b3b06add5cd90c800967a0702a.nq.gz
│   ├── 9fc75617a5b3c069236868def2b819da4713be1f.nq.gz
│   ├── a1b0d589428d667e8aa08b43d6f77506f8625ea9.nq.gz
│   ├── a485625d427fe22dc5597483e2581751cc127516.nq.gz
│   ├── a524c29bdbee3be437bfa8e9e87677942928754b.nq.gz
│   ├── a78fb067056eced8b37447db3b1019f2e780ec5a.nq.gz
│   ├── ab14047dcccecd233d462235caef5d12f79d8dc9.nq.gz
│   ├── abcc3ce35f9b72f0db3229e54ea54eb575a60b3c.nq.gz
│   ├── ad176613f30a708c66a1ffe03e1337d94c628f00.nq.gz
│   ├── b10ec7b946643153cf89b6d24fe772ac08562b13.nq.gz
│   ├── b9723b85ed7adb32f8c2b4ee880c06ec3061da50.nq.gz
│   ├── c50491309fa74f36f3acf7e2aa29a1c2509e839c.nq.gz
│   ├── c86e1127dff522d2de7bd09e366716a8c815aec1.nq.gz
│   ├── c997d19bbc343c66f79df37fb7c8e4f6411ad592.nq.gz
│   ├── d6d33d0e2850578f2bc8269fe908029f988598d0.nq.gz
│   ├── e64adc21a8a81ba599bb4c7b2b103a913150345f.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb3f922b252876b166155bca1b9bbef87b100ae0.nq.gz
│   ├── eed149cad309470781d4b8234e860597574aaab8.nq.gz
│   └── fb36b5ff1f894119f6f19caa9c57cda5b804dfa6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── facfeaf7f8424c35301e218f6e9269a284c9421b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[pypa/dependency-groups](https://github.com/pypa/dependency-groups)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*

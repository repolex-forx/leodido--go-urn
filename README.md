# Repolex Knowledge Graph of leodido/go-urn

RDF knowledge graph data for [leodido/go-urn](https://github.com/leodido/go-urn), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download leodido/go-urn
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d725923fe33ce69c89b9e2033d069099b498224f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d725923fe33ce69c89b9e2033d069099b498224f.nq.gz
│   └── repolex
│       └── d725923fe33ce69c89b9e2033d069099b498224f
│           └── chunk-001.nq.gz
├── blob
│   ├── 08447375a3fc5cc82db436a307af4650ccfd30ae.nq.gz
│   ├── 092cbc1e306d6b1071e7f02695dc5d417d4f8e72.nq.gz
│   ├── 0a17421998eac92be863d01b52e905d375e36c83.nq.gz
│   ├── 0dbfae30e71913670ce4972a99e822c2978d393b.nq.gz
│   ├── 0eeba024e5ef5597239f06c998ce61cba47b2808.nq.gz
│   ├── 134918230ff2f2ad1e78cf6cdd8d0279140fe62f.nq.gz
│   ├── 2b3c13e849d42d02727cfdb6bd56a48321251437.nq.gz
│   ├── 427454f8f1a2e640c0071681ced0c549f5fc7596.nq.gz
│   ├── 4dcac37fc5095ee64644c1a8f31c2231a203211d.nq.gz
│   ├── 53807044fcca03c310e6803791556e13d3190d7f.nq.gz
│   ├── 619475bfbbaad9187b3073366c7fa295f3bc2ec4.nq.gz
│   ├── 68d5dd0f1b36d963dc348fb840dc5ca4cfcb1bd8.nq.gz
│   ├── 735113b9bbf9fe4bf73dd630ff84164cb251ccb6.nq.gz
│   ├── 779cc5d581a2031e630732404acc97480e8bb5de.nq.gz
│   ├── 85639cbb60e06e1efd5766f23b0188a832623648.nq.gz
│   ├── 894d6258dce1a034150786faf4cc09a22441f77a.nq.gz
│   ├── 8c3504a5a9bff4b2c7e92ea2d868430dcba777bd.nq.gz
│   ├── 9ccbdb659dc538e93187f1d4946c24e3ce730fa1.nq.gz
│   ├── aec1ba69cb289f8d094aea8e0acae63bccf9b526.nq.gz
│   ├── b4b768b88e4ed8be325368335fa5f828fa8ad05a.nq.gz
│   ├── b6478e53214dac154a4356e4a68552990d217c95.nq.gz
│   ├── bf83542360a4c029d0dad11eb149d37f23a303e8.nq.gz
│   ├── c543835a286d9c8f627ee508cf71a0251eb50682.nq.gz
│   ├── d1afb302446daf7da2e19fd91d77e2c09feeb786.nq.gz
│   ├── d3c52652656871d9d83f41251db5ade299c2e974.nq.gz
│   ├── d7a0385cea3318e835ca7a1a837b81c508b1fc2b.nq.gz
│   ├── da4dd062e3e2f78183d11ed62252c96c1ca56d5c.nq.gz
│   ├── e3bdc8b3f42986e46f0ffb0a34951866e7af18bf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f5e140f0a43052496a4a119320b92234cbb68e5f.nq.gz
│   ├── f6b7aefbad3eee4cd69503415fe81a1fdaa55b7b.nq.gz
│   ├── f6d60910c2437babe0a43dd6b47fe79f970c0021.nq.gz
│   ├── fa4b6e6825c44c8e114bce85c186b90477400407.nq.gz
│   └── fce5aadc3c8a78756002da720ad6190da9237630.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── d725923fe33ce69c89b9e2033d069099b498224f.nq.gz
├── filetree
│   └── d725923fe33ce69c89b9e2033d069099b498224f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 44 files
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

## Source repository

[leodido/go-urn](https://github.com/leodido/go-urn)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*

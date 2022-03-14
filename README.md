ADR - Architecture Decision Records
===

> ADR - Architecture Decision Records

Inspired by [https://github.com/npryce/adr-tools](https://github.com/npryce/adr-tools), with support for windows.

ADR Blogpost: [Documenting Architecture Decisions](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions)

A good material about [Architecture decision record](https://github.com/joelparkerhenderson/architecture_decision_record)

Forked from [phodal/adr](https://github.com/phodal/adr)

**Features**

 - Supported Windows, GNU/Linux, Mac OS
 - **report for PM, BA**: html, csv, json
 - generate markdown toc（see in [docs/adr](/docs/adr) ）
 - **i18n**: English (en), 中文(zh-cn), Brazilian Portuguese (pt-br), Standard Italian (it-IT), Farsi (fa), French (fr)
 - status logs
 - status query
 - better list view
 - compatible adr-tools
 - custom templates: add a `template.md` file in the save path

HTML Reporter Example
---
 
 - [ADR Example](https://phodal.github.io/adr/examples/export-1.html)
 - [ADR Tools Example](https://phodal.github.io/adr/examples/export-3.html)
 - [会分期 Example](https://phodal.github.io/adr/examples/export-2.html)
 - [Arachne Framework Example](https://phodal.github.io/adr/examples/export-4.html)
 
Install
---

1. install

```
npm install -g @uniplato/adr
```

2. init

```
adr init <language>
```

e.x: ``adr init 'en'``

### new

```bash
adr new <decision>
```

e.x: ``adr new "create project"``

### list

```bash
adr list
```

result:

```
╔══════════════════════════════════════╤══════════════╤═══════════════════╗
║ Decision                             │ Last Modified│ Last Status       ║
╟──────────────────────────────────────┼──────────────┼───────────────────╢
║ 1.编写完整的单元测试                    │ 2017-11-26   │ 2017-11-26 已完成  ║
╟──────────────────────────────────────┼──────────────┼───────────────────╢
║ 2.添加目录生成                         │ 2017-11-26   │ 2017-11-25 已完成  ║
╟──────────────────────────────────────┼──────────────┼───────────────────╢
║ 3.图形生成功能                         │ 2017-11-26   │ 2017-11-24 已完成  ║
╟──────────────────────────────────────┼──────────────┼───────────────────╢
║ 4.生成在线图形                         │ 2017-11-26   │ 2017-11-22 提议    ║
╚══════════════════════════════════════╧══════════════╧═══════════════════╝
```

### generate graph

```
adr generate graph
```

results:

```
digraph {
  node [shape=plaintext];
  _1 [label="1.编写完整的单元测试"; URL="001-编写完整的单元测试.md"]
  _2 [label="2.添加目录生成"; URL="002-添加目录生成.md"]
  _1 -> _2 [style="dotted"];
  _3 [label="3.图形生成"; URL="003-图形生成.md"]
  _2 -> _3 [style="dotted"];
}
```

### decisions change logs

```
adr logs <index>
```

e.x. ``adr logs 9``

```
╔════════════╤══════╗
║  -         │  -   ║
╟────────────┼──────╢
║ 2017-11-23 │ 提议 ║
╟────────────┼──────╢
║ 2017-11-24 │ 通过 ║
╚════════════╧══════╝
```

### export adr

support: json, csv, html, markdown

```
adr export <type>
```

e.x. ``adr export csv``

```
Index, 决策, 上次修改时间, 最后状态
1, 编写完整的单元测试, 2017-11-26, 2017-11-26 已完成
2, 添加目录生成, 2017-11-26, 2017-11-25 已完成
3, 图形生成功能, 2017-11-26, 2017-11-24 已完成
```

### search adr

```
adr search <keyword>
```

e.x. ``adr search 测试``

```
╔══════════════════════╤══════════════════╗
║ 决策                 │ 最后状态         ║
╟──────────────────────┼──────────────────╢
║ 19.添加-e2e-测试     │ 2017-11-28 提议  ║
╟──────────────────────┼──────────────────╢
║ 1.编写完整的单元测试 │ 2017-11-26 完成  ║
╚══════════════════════╧══════════════════╝
```

Config
---

current:
 
  - **language**, language
  - **path**, save path
  - **digits**, the index length, e.x. digits:3 001-index.md
  - **prefix**, the prefix of files, e.x. adr-0001

example config: 

```
{
  "path":"doc/adr/",
  "language":"zh-cn",
  "prefix": "",
  "digits": 4
}
```

License
---

@ 2022 Forked by Amir Asghary from Uniplato

@ 2017~2021 A [Phodal Huang](https://www.phodal.com)'s [Idea](http://github.com/phodal/ideas).

This code is distributed under the MIT license. See `LICENSE` in this directory.

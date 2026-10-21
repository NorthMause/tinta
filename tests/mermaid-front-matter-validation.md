# Mermaid diagrams with front matter (#261)

Validated on Windows with the Release build on 2026-10-21.

## Problem

The reporter's diagram was an ER diagram that showed as source. The first
example in Mermaid's ER documentation opens with YAML front matter:

```text
---
title: Order example
---
erDiagram
    CUSTOMER ||--o{ ORDER : places
```

Tinta's type detection skipped the two `---` lines but read the YAML
between them as the diagram's first line, so `title:` decided the type, it
matched none, and the fence fell back to source. The same happened to any
diagram with a `title` or `config` block, of every type.

## Change

- `mermaidext::skipFrontMatter` returns the source after a front matter
  block: a `---` line preceded only by blank lines (and a byte order mark),
  through the next `---` line. An unclosed block, or a `---` line after the
  diagram has started, is not front matter.
- Type detection and every non-flowchart renderer read the diagram after
  it. The flowchart parser blanks the block instead, keeping its line
  breaks, so a parse error still reports the fence's own line number.
- The HTML and Word exports and the copy-as-image button go through the
  same functions.

## Automated checks

- `mermaid_parser`: `tests/fixtures/mermaid-front-matter-261.md` holds a
  flowchart, a sequence diagram, a pie, a class and a state diagram with
  front matter, then the 25 examples of Mermaid's ER documentation in order.
  Each fence is detected and built as the app does. The 16 that should draw
  draw: every front matter fence (including ER docs 1, 4 and 25) and the
  other ER examples whose syntax is supported. The other 14 show their
  source. Edge cases: a byte order mark, a blank line, CRLF and trailing
  spaces; an unclosed block; a `---` edge after the header; an empty block;
  a flowchart error line after front matter.
- `code_block_layout`: the same fixture laid out by the app, in two themes,
  two scales and two widths, gives diagram blocks for exactly those 16
  fences, and the text after the last diagram lays out.

Making `skipFrontMatter` return its input fails all eight front matter
fences in both suites (12 parser checks, 64 layout checks).

Of the 25 ER documentation examples, 11 drew after this change, against
8 before.

## Built app

A portable copy of the Release `tinta.exe` exported the fixture with
`--exporthtml` (`out/desktop-check-1021/`, ignored): 16 diagrams came out
as inline SVG and 14 fences as source, none of them with front matter.

## Limits

- The front matter `title` is not drawn above the diagram, as Mermaid
  does; the diagram itself is. `config` (theme, look, layout) is ignored.
- ER syntax that still shows source, from the same documentation page:
  cardinalities written in words (`1 to zero or more`, `only one to zero
  or more`), a quoted entity on its own (`"This ❤ Unicode"`, Markdown in
  entity names), subgraphs, `style`, `classDef` and `:::class`.

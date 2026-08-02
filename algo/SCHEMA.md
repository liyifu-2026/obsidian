# Wiki Schema

## Domain
算法与数据结构学习知识库

## Conventions
- File names: lowercase, hyphens, no spaces (e.g., `binary-search.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md` under the correct section
- Every action must be appended to `log.md`
- **Provenance markers:** On pages that synthesize 3+ sources, append `^[raw/articles/source-file.md]` at the end of paragraphs whose claims come from a specific source.

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/articles/source-name.md]
confidence: high | medium | low
contested: true
contradictions: [other-page-slug]
---
```

## Tag Taxonomy
- Algorithms: sorting, searching, graph, dynamic-programming, greedy, divide-and-conquer
- Data Structures: array, linked-list, stack, queue, tree, hash-table, heap, graph
- Complexity: time-complexity, space-complexity, optimization
- Applications: leetcode, interview, practical

## Page Thresholds
- **Create a page** when an entity/concept appears in 2+ sources OR is central to one source
- **DON'T create a page** for passing mentions or minor details
- **Split a page** when it exceeds ~200 lines

## Update Policy
When new information conflicts with existing content:
1. Check the dates — newer sources generally supersede older ones
2. If genuinely contradictory, note both positions with dates and sources
3. Mark the contradiction in frontmatter: `contradictions: [page-name]`

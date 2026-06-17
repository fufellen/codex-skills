---
name: knowledge-refactoring
description: Refactor Obsidian vault notes and other knowledge bases into linked sources of truth. Use when the user asks to remove duplicates, consolidate notes, choose canonical notes, replace repeated explanations with [[Obsidian links]], audit stale facts against source files or code, or reorganize technical knowledge without moving files.
---

# Knowledge Refactoring

## Core Rule

Make knowledge DRY without making it cryptic. Each durable fact should have one canonical home; other notes should mention the concept briefly and link to the canonical note or section.

## Workflow

1. Search the relevant folder first, then widen the search only as needed.
2. Identify duplicated claims, tables, code layouts, procedures, and checklists.
3. Assign a role to each note before editing:
   - canonical specification;
   - route map or workflow;
   - audience summary;
   - diagnostic checklist;
   - archive or historical context.
4. Keep complete details only in the canonical note. In other notes, replace duplicated details with `[[Note]]` or `[[Note#Section]]`.
5. Preserve unique context: decisions, caveats, chronology, diagnostics, and project-specific warnings should not be deleted just because related facts are canonical elsewhere.
6. When a note describes software, protocols, schemas, hardware behavior, or APIs, verify the canonical facts against the actual source files before treating them as truth.
7. Do not move or rename notes unless the user explicitly asks.
8. After material edits, run the vault note validator when available.

## Canonicalization Heuristics

- Put byte layouts, packet formats, constants, enum mappings, and selectors in one specification note.
- Put end-to-end procedures in a route-map note that links to the specification sections.
- Put troubleshooting in a diagnostic note or section, linking to the relevant specs instead of copying field lists.
- Put human-facing briefings in short summary notes with links to the authoritative details.
- If two notes both look canonical, choose the one whose title names the concept most directly, then turn the other into a workflow, index, or summary.

## Obsidian Links

Use exact wiki links for local notes:

```text
[[Canonical Note]]
[[Canonical Note#Section]]
[[Canonical Note|display text]]
```

Do not write meta-comments inside notes such as "removed duplication here". Make the note read naturally.

## Verification

For technical refactors:

- cite source paths inside the note when they are useful for future checking;
- distinguish verified facts from hypotheses;
- remove or qualify stale statements that no longer match source code;
- prefer source code, primary docs, and generated artifacts over memory.

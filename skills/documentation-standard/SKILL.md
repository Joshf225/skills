---
name: documentation-standard
description: Use when writing or reviewing project documentation: decision records, ticket notes, handoffs, completion records, research notes, or glossaries. Keep decisions and evidence concise, linked, and easy to review across projects.
---

# Documentation standard

Write the shortest document that preserves decisions, constraints, reasons, evidence, and follow-up work. Every retained line should change a reader's understanding or future action.

## Workflow

1. Identify what readers need to decide, verify, or do later. Find the project's existing documentation rules, templates, vocabulary, and authoritative files first; use those conventions when they exist.
2. Locate the source of truth for each fact. Usually the issue holds scope and acceptance criteria; a decision record holds approved choices and reasons; code and tests hold implemented behavior; a handoff holds current status; research notes hold detailed evidence. Adapt this map to the project. Update the authority or link to it rather than making a competing copy.
3. Choose the smallest deliverable the work needs. Put the decision or rule first, followed by only the rationale needed to distinguish it from a real alternative. Keep necessary invariants, failure outcomes, security boundaries, unresolved risks, sources, and follow-up obligations explicit.
4. Review every changed document line by line using the checklist below. Record the self-review result in the project's active handoff or review state when it has one.

## Writing rules

- Give each paragraph one job: decision, constraint, reason, consequence, evidence, or follow-up.
- Prefer short tables for parallel choices and short bullets for independent rules. Link primary sources for standard technology explanations; write project-specific conclusions in the document.
- Record rejected alternatives only if they were plausible or prevent a likely reversal. Keep examples only if they remove ambiguity.
- Omit empty sections, ceremonial introductions, repeated issue text, implementation diaries, and generic best-practice explanations.
- Use the project's canonical terms. Update its glossary only when a decision establishes or changes vocabulary.
- Keep a draft's TL;DR near the top and current: a short paragraph or 3–5 bullets, normally under 100 words.
- Treat length as a review signal, not a gate. Decision records often fit in 600–900 words; longer is fine when contracts, matrices, or safety constraints need room. Move optional investigation behind a precise link rather than removing a necessary detail to reach a word count. Judge writing by eye, not automated word-count or style gates.

## By deliverable

- **Decision record:** Use the project's template if present. Capture final choices, decisive reasons, implementation constraints, meaningful rejected alternatives, unresolved questions, follow-up work, and sources. Mark proposals distinctly from approved decisions. Make it a record, not a tutorial.
- **Implementation ticket:** Let code and tests carry implementation detail. Update the issue and current handoff; add a concise delivery record after approval or merge if the project tracks one. Write a separate narrative report only when requested or required.
- **Handoff or completion record:** State ownership, review state, checks, outcome, decisions, and next work briefly. Link deliverables instead of retelling them. Keep active state separate from historical completed work if the project uses both.
- **Research note:** Preserve useful detailed evidence behind a concise TL;DR. Map claims to primary sources. Link only the relevant findings from the decision record.
- **Glossary entry:** Define a project term in one or two sentences; list rejected synonyms if useful. Keep vocabulary separate from specifications and implementation guides.

## Completion review

Before marking documentation ready for review, answer each question for every changed document:

1. Does each line affect a decision, constraint, review, or future action?
2. Is a fact repeated from an authoritative issue, glossary, handoff, code, or research note instead of linked?
3. Can a later reader distinguish approved decisions from proposals and unresolved questions?
4. Are invariants, failure outcomes, security boundaries, and follow-up obligations still explicit?
5. Can background or evidence move behind a link without harming the main reading path?
6. Does the TL;DR still match the document, and are project terms consistent?

The project owner's review is the final quality check. Fold recurring feedback into the project's standard when it has one.

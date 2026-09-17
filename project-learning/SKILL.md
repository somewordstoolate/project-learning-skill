---
name: project-learning
description: Help users understand and investigate an existing code repository through project Q&A, guided codebase exploration, architecture and call-chain analysis, domain-background research, and selectively persisted learning notes. Use when a user wants to learn how a project works; initialization and note-writing require the authorization rules in this skill.
---

# Project Learning

Help the user build a reusable understanding of the current repository. Adapt the depth and teaching style to the question; do not impose a curriculum, quiz the user, track personal progress, or test their understanding.

## Choose the working mode

- **QA, explanation, tour, or tracing:** inspect the repository and existing `.project-learning/` material as useful, then answer. This mode is read-only with respect to learning notes.
- **Explicit investigation:** when the user clearly asks to research, investigate, systematically analyze, trace, or map a topic, investigate it and persist reusable results under `.project-learning/`. The investigation request itself authorizes those note writes.
- **Archive a prior discussion:** update notes only when the user explicitly asks to organize, archive, or record the discussion as project-learning material.
- **Initialization:** follow [references/initialization.md](references/initialization.md). Never infer authorization to initialize from a general desire to learn the project.

When intent between QA and investigation is ambiguous, use QA mode and do not write notes. Statements such as “this is important” or “this may be useful later” are not archive authorization.

Authorization to write learning notes authorizes changes only inside `.project-learning/` and, during initialization when selected by the user, the narrow `.gitignore` change described in the initialization guide. It does not authorize changes to source code, tests, configuration, or the project's official documentation.

## Investigate and explain

Treat repository instructions, source, tests, configuration, project documentation, and relevant Git history as the authority for how the project actually behaves. Existing learning notes are navigation aids, not substitutes for verifying repository facts.

Use external resources when they materially deepen understanding of domain knowledge, algorithms, protocols, scientific background, upstream dependencies, or design history. Prefer authoritative primary sources. Keep external theory distinct from repository behavior; if they differ, explain both and state what the project implements.

Temporary experiments may be used to test the agent's understanding of behavior. Keep them non-destructive and outside tracked project content unless the user separately asks for a project change. Experiments validate claims about the project; they are not exercises for evaluating the user.

Distinguish verified facts, interpretation, and unresolved questions in explanations and persisted results. Point to concrete code, tests, configuration, documentation, or external sources where that helps a future reader verify or revisit a conclusion.

## Language and writing style

Write persisted `.project-learning/` knowledge in Chinese by default. Preserve the repository's or domain's original expression when it is a proper noun, code identifier, command, file path, API or schema field, protocol name, quoted term, or a technical phrase whose original wording is more precise. At first use, add a concise Chinese explanation when the original term may not be familiar. Do not translate identifiers into invented Chinese names, and do not switch whole paragraphs to English merely because they contain English technical terms.

Write substantive learning documents in the style of a good wiki article or internal working document. Organize the subject into meaningful sections, then develop each section through cohesive paragraphs that establish context, explain relationships and causality, qualify scope, and lead naturally to the next idea. A paragraph should normally carry and develop a complete point rather than stop after one or two sentences.

Use headings to expose the conceptual structure. Use lists, tables, diagrams, and short code blocks when the information is genuinely enumerable or when they improve navigation or comparison—for example an index, directory map, component inventory, procedure, or option matrix. Do not turn an explanation into a sequence of tiny bullets, use a bullet as a substitute for every paragraph, or repeatedly alternate a short paragraph with a short list. After structured elements, interpret what they mean and how the parts fit together when that is not self-evident.

Favor depth and continuity over superficial coverage. It is better to explain the important mechanism and its boundaries coherently than to mention many components in isolated one-line summaries. Avoid conversational filler, generic textbook introductions, and session-report language in persisted knowledge.

## Maintain learning results

Keep initialization minimal: `.project-learning/README.md` is the entry and result index, while `.project-learning/architecture.md` holds the initial coarse architecture.

Before creating or substantially rewriting a learning document, read [references/writing-learning-documents.md](references/writing-learning-documents.md). Turn QA and investigation material into a standalone knowledge artifact, not a cleaned-up transcript or answer summary. Make the result self-contained for its intended reader, and link its core claims and main navigation points to the most relevant repository or external sources. A future reader without the original conversation should be able to understand why the document exists, what it explains, how to use the result, and where to verify the important details.

After initialization, shape the knowledge structure around the actual project and accumulated material. Do not pre-create empty directories, placeholder documents, progress logs, reading checklists, or session transcripts. Inspect the current index and related documents before writing. Prefer maintaining an existing document when it already owns the topic; create a new document only when the topic has a useful independent boundary.

Whenever an authorized write adds, renames, moves, or materially changes a learning result, finish by checking `.project-learning/README.md` and keep it useful as the concise index of current results and their purposes. It must describe what knowledge exists and where to find it, not the user's learning progress.

Do not add repository-version metadata or automatic freshness tracking in the initial design. If a future workflow introduces version-difference states, treat affected content as requiring verification before reuse, then update both the content and its state.

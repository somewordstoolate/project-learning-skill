# Writing and maintaining learning documents

Read this guide before creating a learning document from QA or investigation results, or before substantially restructuring an existing one.

## Produce a standalone knowledge artifact

Archiving QA is not the act of preserving an answer. Reconstruct the useful knowledge so the result makes sense without the original conversation. Before writing, identify the question the document answers, the level at which it answers it, the useful boundary of the topic, and the mental model a reader should leave with. These decisions guide the article but do not need to appear as a questionnaire or a fixed metadata block.

Organize material in knowledge order rather than conversation order. Supply context that was implicit in the exchange, remove conversational detours, and connect claims that only made sense because earlier chat turns were visible. Do not preserve a transcript, lightly edit a response, or collect several correct but disconnected conclusions under headings.

## Make the document self-contained for its intended reader

A learning document must be understandable without the original conversation, hidden investigation context, or an unexplained dependency on another note. Introduce the vocabulary, actors, data shapes, and assumptions needed to follow the central explanation. When a compact source fragment would otherwise require the reader to infer how it becomes real data or behavior, translate it into a concrete example, small diagram, pseudo-type, or before/after shape and explain what each important part means.

When the subject is specialized and several domain terms, abbreviations, or repository-specific words are prerequisites for the rest of the document, establish a small conceptual vocabulary near the opening. Define each term in plain language, preserve the exact original identifier or technical expression, and explain distinctions that the later argument depends on. Prefer a short framing paragraph or compact table over a ceremonial glossary. If only one or two unfamiliar terms occur, explain them at first use instead; do not force every document to begin with a terminology section.

Choose terms by dependency, not by frequency alone: include the concepts a reader must understand to follow the document, and omit jargon that is incidental or already obvious to the intended audience. Keep introductory definitions provisional enough for entry but accurate enough that later sections do not need to undo them; develop their subtleties where the relevant mechanism or example appears.

Self-contained does not mean exhaustive or source-free. State the document's boundary, explain everything needed inside that boundary, and link outward for optional depth or authoritative detail. Do not reproduce large source files, repeat substantial explanations already owned by another learning document, or expand every technical term regardless of audience. A cross-link is appropriate for a secondary branch; a concept required to understand the current document still needs a concise local explanation before that link.

## Link core claims and navigation points to sources

Add clickable links for the sources a reader is most likely to need in order to verify, inspect, or continue from the document. In particular, link the authoritative schema, source file, test, configuration, project decision, formal documentation, representative example, or external primary source behind a core claim when one exists. Also link the main next-reading destinations instead of mentioning only bare paths or titles.

Prefer links at the first substantive use or next to the claim they support, with descriptive link text. Use repository-relative Markdown links for local files so the document remains navigable with the repository, and direct links to authoritative pages for external material. A code-formatted path may still be useful when the exact path is itself part of the explanation, but it should not be the only navigation mechanism for a core or highlighted source.

Links are selective evidence and navigation, not decoration. Do not link every incidental identifier or repeat the same destination on every mention. Distinguish a source that establishes repository behavior from background material that only explains the surrounding theory, and avoid implying that an example proves a broader rule than its source supports.

## Give the reader an entry and an exit

Open with whichever of these best fits the document:

- a short background that explains where the problem comes from, why it matters, and what the document covers; or
- a concise summary that states what the document answers and its central result.

Do not require both. Avoid ceremonial introductions and generic background that does not help the reader enter the actual topic.

Close the document lightly. Use a short synthesis, a small set of directly relevant follow-up directions, links to related learning results or authoritative project sources, or a combination of these. The ending should make the document's result and practical use clear, but it should not launch a second deep investigation or inflate a small note into a comprehensive guide.

The body should normally move from the framing or summary into the conceptual model, important relationships or mechanisms, and supporting examples or repository evidence. This is a semantic progression, not a mandatory section template. Choose headings that fit the subject.

## Use examples without letting them define the rule

State what an example is intended to illustrate. Give the reader enough general framing to distinguish the reusable model from details peculiar to the example, and return from the example to the general conclusion when the transfer is not obvious. Preserve exact repository identifiers where they matter for lookup or behavior.

Do not generalize an example's accidental properties into a project-wide rule. When a statement is true only for the example, qualify it locally rather than weakening the entire article with repeated disclaimers.

## Maintain the existing knowledge base

Before writing, read `.project-learning/README.md` and inspect documents whose scope overlaps the new material. Decide among four actions based on topic ownership:

- **Update:** the result belongs naturally inside an existing document's question and scope.
- **Create:** the result has a useful independent boundary and would distract or overload the existing document.
- **Split:** an existing document combines subjects that have become independently useful.
- **Cross-link:** related documents need navigation between them, but duplicating their explanations would create competing sources.

Prefer updating over creating when an existing document already owns the subject. When updating, edit the article as a whole: place the material where it belongs, reconcile duplication or disagreement, and revise the opening, section transitions, conclusion, and related links when the new knowledge changes them. Do not merely append the newest answer at the end.

Apply improved writing conventions progressively. Do not rewrite untouched historical documents solely to conform to a newer style. When a task uses an older document, improve only the portions and surrounding structure needed to integrate the new result coherently. Preserve still-useful knowledge and avoid unrelated churn.

After any authorized write, check whether `.project-learning/README.md` accurately indexes the learning results that now exist. Add, update, move, or remove index entries to match the actual structure.

## Final read-through

Read the result once as a future reader who has not seen the source conversation. Confirm that the reader can tell why the document exists, what scope and model it establishes, how its sections connect, and what conclusion or practical use follows. For specialized topics, check that prerequisite terminology is introduced before it is relied upon and that the opening does not contain an unnecessary glossary of incidental jargon. Check that every concept required for the main argument is introduced locally, that core claims and important next-reading destinations have useful clickable links, and that those links resolve to the intended targets. Fix missing context and abrupt endings through targeted editing; do not respond by adding filler, unnecessary headings, or more lists.

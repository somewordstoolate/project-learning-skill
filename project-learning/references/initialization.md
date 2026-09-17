# Initialize project learning

Initialization creates a repository-local learning space. It is a write operation and requires explicit authorization.

## Authorization gate

If the user has not explicitly authorized initialization, ask exactly one sentence and take no initialization action:

> 是否初始化当前仓库的项目学习空间？如确认，请回复：`确认初始化项目学习空间`

Proceed only after the user replies with `确认初始化项目学习空间`. Do not treat “可以”, “开始吧”, a request to understand the repository, or other approximate wording as authorization.

This gate controls creation or modification of `.project-learning/`; it does not prevent read-only project-learning QA before initialization.

## Collect initialization choices

After authorization, determine these two project-local choices. Ask concisely if the user has not already supplied them:

1. **Depth**
   - **Quick:** read repository instructions, primary README files, and the top-level structure.
   - **Standard (recommended):** additionally inspect entry points, core modules, configuration, tests, and common commands.
   - **Deep:** additionally trace important data flows, run necessary non-destructive commands, inspect relevant Git design history, and use external material when domain background is necessary.
2. **Git policy:** whether `.project-learning/` should be committed. Do not assume one project's answer is a global preference.

Depth changes analysis depth, not the number of initialized files.

## Inspect before writing

Read all repository agent instructions that apply to the working directory before inspecting or writing. Check whether `.project-learning/` already exists and preserve useful existing content. Never replace an existing learning space as though it were empty.

If the user chooses not to commit the learning space, inspect `.gitignore` and add the narrow root entry `/.project-learning/` if needed. If files there are already tracked, explain the situation and do not untrack them without separate authorization.

If the user chooses to commit it, do not remove an existing ignore rule silently; surface the conflict and ask for direction because changing ignore policy can expose existing personal notes.

## Minimal initialized result

Create only:

```text
.project-learning/
├── README.md
└── architecture.md
```

Do not create empty topic directories or speculative documents.

`README.md` is the learning-space entry point. Keep it coarse and include:

- a short statement of the learning space's purpose;
- a concise index of current learning results and what each is useful for;
- a link to `architecture.md`.

Do not include personal progress, completed-reading lists, study plans, or session logs.

Write the learning space in Chinese. Keep repository and domain proper nouns, code identifiers, paths, commands, API names, schema fields, and other precise technical expressions in their original form where appropriate. The index may use a compact list or table because its purpose is navigation.

`architecture.md` records only the architecture justified by the chosen inspection depth, such as major directories, entry points, core components, their relationships, and important data flows. Mark uncertainty instead of filling gaps with guesses.

Write `architecture.md` as a coarse wiki-style architecture article, not as a generated inventory report. Use sections to separate major concerns and cohesive paragraphs to explain component responsibilities, relationships, control flow, and data flow. Directory lists, component tables, and diagrams are useful supporting structures, but they must not replace the explanatory narrative. Avoid one- or two-sentence paragraph fragments followed by another list when the ideas belong in one sustained explanation.

Keep both documents intentionally rough at initialization. Later explicit investigations or archive requests can update them or introduce a structure suited to the project.

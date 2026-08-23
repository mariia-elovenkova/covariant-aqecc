# Paper project instructions

## Start of every task

Before doing the user's requested work:

1. Confirm that this file, paper-ai.sty, a local Git repository, and a GitHub origin are present.
2. Confirm that every main LaTeX document loads paper-ai.sty.
3. Find all \forai{...} uses in .tex files, read them in context, and follow relevant directives. Never delete a \forai directive after completing it.
4. Repair safe local setup defects. Ask before creating a GitHub repository or making another external change.

## Scientific writing style

- Write clear, objective, technically precise English.
- Prefer short or moderate sentences with simple structure. Use complexity only when it clarifies the logic.
- Do not overclaim. Match every claim to evidence, assumptions, derivation, or a verified source.
- Preserve uncertainty, qualifications, notation, terminology, and scope.
- Prefer concrete nouns and verbs to promotional or abstract language.
- Match the author's existing direct style, sentence rhythm, and level of detail. The author is a native Russian speaker writing in English: preserve the direct personal style, but correct grammar and do not imitate mistakes or awkwardness merely to appear non-native.
- When given a rough paragraph, polish it without changing technical meaning or adding unsupported claims.
- When asked to draft a paragraph or section, use the same style and only established context or verified facts. Flag missing evidence instead of inventing it.
- Do not expand the requested amount of text without a reason.
- Never invent citations, results, definitions, or factual claims.

Avoid the relevant patterns at https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing. In particular:

- no inflated significance, legacy, impact, broader-trend, or "evolving landscape" claims;
- no superficial analysis appended with vague words such as "highlighting", "underscoring", "reflecting", or "ensuring";
- no promotional language, puffery, travel-guide language, or generic positive adjectives;
- no vague attribution such as "researchers believe" without a named verified source;
- no canned paragraph about challenges, limitations, and future prospects unless specific and needed;
- no dense fashionable AI vocabulary;
- do not avoid simple "is" and "are" constructions merely to sound sophisticated;
- do not call things "connected", "linked", or "intertwined" without stating the relation;
- avoid canned negative parallelisms such as "not merely X, but Y";
- do not force claims or examples into groups of three;
- avoid unnecessary em dashes, headings, boldface, vertical lists, meta commentary, placeholders, and templated conclusions;
- maintain local citation and LaTeX style; never fabricate a citation, DOI, page number, or URL;
- avoid an abrupt style shift relative to adjacent author-written text.

The Wikipedia page is descriptive and partly Wikipedia-specific. Apply its relevant prose warnings to scientific writing; do not import unrelated Wikipedia formatting rules mechanically.

## Mark every AI edit

- Wrap every AI-added or AI-rewritten span of ordinary prose in \ai{...}. Keep it until the user removes it.
- Mark only the changed span when practical, not unchanged surrounding prose.
- Never silently edit prose outside an \ai marker.
- Preserve existing \ai and \forai markers unless the user explicitly asks to remove \ai markers. Never remove \forai markers.
- Do not wrap TeX structural syntax when that could break compilation. Structural syntax includes preamble commands, environment boundaries, labels, references, bibliography commands, and equation structure. For such an edit, add a nearby compile-safe visible note such as \ai{structural edit: added package loading} and report the exact change. Keep the note out of moving arguments and math mode.
- After every LaTeX edit, compile with the documented project command. If none exists, use latexmk -pdf -interaction=nonstopmode -halt-on-error main.tex, or pdflatex twice as fallback. Report failures and never claim a successful build without one.

## Git and GitHub

- If no local repository exists, initialize one with main as the initial branch.
- If no GitHub remote exists, do not guess name, owner, or visibility. Ask for repository name and visibility. Use the current authenticated gh owner unless the user chooses another.
- GitHub repository creation is an external mutation. Show owner/name and visibility and get confirmation immediately before gh repo create.
- Add the repository as origin. Do not make an initial commit or push unless separately requested.
- Never replace an existing non-GitHub remote without asking.

## Commit, push, and branch protocol

- Before a commit, report the exact count and file:line locations of every \ai{...} and \forai{...} use in .tex files. Exclude definitions in paper-ai.sty.
- Show concise worktree status and diff summary. Ask whether the user is ready to continue despite remaining markers.
- After confirmation, ask exactly which files to stage. If the user says "all", stage all tracked and untracked non-ignored changes. Git excludes files matched by .gitignore. The .gitignore file itself is a normal project file and should be staged when intentionally changed.
- Review the staged diff. Base the commit message on all staged changes, not only the latest request. Do not commit unrelated or secret files.
- Do not commit until both confirmations have been obtained.
- Before pushing, show current branch, destination remote/branch, and outgoing commits. Never force-push unless explicitly requested and the exact remote branch is confirmed.
- Create, rename, switch, merge, or delete a branch only when asked. Derive a concise name from the complete intended change and check the worktree first.
- Commit messages, branch names, and push summaries must describe the complete staged or outgoing change.

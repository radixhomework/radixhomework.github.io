# AGENTS.md — working rules for coding agents

Rules for AI agents (and anyone acting as one) working in this repository.
This is the RadixHomeWork website: a small Jekyll / GitHub Pages site.
Project-specific details live in the README.md — read it before touching
code.

## Commit policy

- **Commit and push only on the user's explicit demand.** Finishing a
  task or passing tests is never consent to commit.
- **Sole exception — quality-check rounds**: when the user asks for a
  quality check (or when a quality-fix loop below is running), the agent
  is autonomous: it commits and pushes its fixes on its own so they can
  be verified, without asking each time. That autonomy covers the
  quality-check scope only — never anything unrelated to the findings.
- If the user asks to hold for local testing, report "done, ready to test"
  and stop — don't ask again; wait for an explicit go.
- Short descriptive commit messages in English, sentence style
  (e.g. "Add Simple VTT project page"). This is the repository's own
  practice and prevails over any generic convention.
- Work is committed and pushed to `main` when the user asks for it.
  Feature branches (`feat/*`) only when the user explicitly requests one.
- When the working tree contains files the agent did not create, inspect
  them and say so before staging everything.

## Agent-local files are never committed

- **Never stage or commit agent-specific directories and files**
  (`.zcode/`, `.claude/`, `.agents/`, `.cursor/`, `.aider*`, and the like).
  They are machine-local configuration, not project content. The repo
  `.gitignore` covers them; if it doesn't yet, propose adding it rather
  than committing these paths.

## Quality gates

There is no SonarCloud, CodeQL or CI review setup in this repository; the
effective quality gate is:

1. `bundle exec jekyll serve` builds the site without errors.
2. The affected pages render correctly in the browser (or a build of the
   site passes when a browser check isn't practical).

Fix what a quality check reports, verify, and repeat — **3 iterations
maximum, autonomously**, committing each fix per the Commit policy
exception. After 3 fix/verify rounds, stop and report the remaining
findings and what was tried; wait for the user's decision.

## Testing stance

- Do not build heavy test suites unless asked (this repo has none).
  Verify by building the site with Jekyll and exercising the real pages.
- When the user says to do fewer tests and move on, move on — don't stall
  on ceremony.

## Product & architecture documentation

`PRODUCT.md` and `ARCHITECTURE.md` are not present in this repository.
Given the site's size, the README.md is the project documentation; keep it
accurate when structure or workflows change. If the repository grows to
the point where a PRODUCT.md / ARCHITECTURE.md split is warranted, propose
it to the user rather than creating the files unasked.

- When starting a task, read the README and `_config.yml` first; if the
  code and the docs disagree, surface the discrepancy to the user instead
  of silently trusting either one.

## Documentation edits need approval

`AGENTS.md` is never edited silently: substantive changes (new decisions,
scope changes, removed sections) are proposed to the user and applied
after approval. Routine sync of facts that an approved change already
implies goes in directly.

## Keeping this file honest

Delete any section that doesn't apply to this repository anymore, and add
repo-specific sections (stack conventions, build commands) below.

### Build & preview

```bash
bundle install
bundle exec jekyll serve
```

Design tokens (colors, fonts) live in `assets/css/style.scss`; the brand
palette and the Cormorant Garamond / Source Sans 3 fonts must stay
consistent with the RadixHomeWork visual identity.

# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## Project

`plan-marshall-documentation` holds every document of plan-marshall-mcp (PM-MCP): requirements in
`doc/Requirements.adoc` (modules in `doc/requirements/`), technical specifications in `doc/Specification.adoc`
(documents in `doc/specification/`), delivery staging in `doc/roadmap.adoc`, defect archetypes and fixtures to guard
during implementation in `doc/ImplementationWatch.adoc` (documents in `doc/implementation-watch/`), and the concept,
developer and user documentation of the implemented system. It holds no code and builds no artifact.

The code lives in four repositories of the organisation `plan-marshall`: `plan-marshall-mcp` (the Quarkus daemon
assembly `pm-mcp-server`, the end-to-end tests, the model verification corpus `test/model/verification/`),
`pm-mcp-core` (the plain-Java engine), `pm-mcp-clients` (the client contract and the client binaries) and
`pm-mcp-parent` (the parent POM). The only listing of the repositories and modules is
`doc/specification/module-structure.adoc`; name modules from there and never repeat the listing elsewhere.

## Project Setup

`doc/developer/project-setup.adoc` is the reference for how the project is organised and worked on, in this repository
and in the four code repositories: the repositories and their checkouts beside each other, building, how the
repositories depend on each other in practice, what every repository is set up with, how the work is planned as work
packages, and how a change gets from a branch to `main`. Read it before starting work. This file holds only what is
specific to this repository; keep the two consistent, and change the reference when the setup changes.

What waits for a decision of the operator is listed in `doc/discussions/open-questions.adoc`. Read it with the
reference, add a question there instead of deciding it silently, and remove a question once its decision is written
into the documents it concerns.

## Documentation

AsciiDoc (`.adoc`) for all project documentation. Requirements go into `doc/requirements/`,
technical specifications into `doc/specification/` (traceability rules in `doc/Specification.adoc`; a reference
specification with status `REFERENCE`, such as `evaluation.adoc`, records evidence and defines nothing),
research notes and open proposals into `doc/discussions/` (a decided proposal is applied and then deleted).
The normative documents state the target only: no decision ids, decision dates, or history narration.
Model roles are verified against the corpus `test/model/verification/` (`validate.py`).
Documentation of the implemented system goes into three trees: concepts (`doc/Concepts.adoc`, `doc/concepts/`), developer (`doc/DeveloperGuide.adoc`,
`doc/developer/`) and user (`doc/UserGuide.adoc`, `doc/user/`). Don't create new documents without asking,
except topic documents inside those three trees written by `traced-implementation`.

Every concrete implementation follows the project skill `traced-implementation`: each planned task traces
to its requirements, specification sections and watch items (the _Implementation watch_ line below a
heading, plus `doc/implementation-watch/cross-cutting.adoc`) and assigns each specified statement its
destination (code, test, concept, developer or user documentation); after implementation, coverage is
verified against all three; a requirement the implementation proves wrong is corrected (with evidence) in
the same plan, never worked around in code; the same PR writes the concept, developer and user
documentation for the slice from the specification and watch corpus (describing the implemented system,
verified against the code), deletes the implemented specification sections and watch items, and links each
requirement to its classes, tests and documentation (`Implementation:` / `Verified by:` / `Documentation:`
lines).

### Links

- Links inside `doc/` are relative.
- A link from a document into code (`Implementation:`, `Verified by:`) is an absolute link
  `https://github.com/plan-marshall/<repository>/blob/main/<path>` to the repository that owns the file.
- Code and the `CLAUDE.md` of a code repository link into this repository with an absolute link
  `https://github.com/plan-marshall/plan-marshall-documentation/blob/main/doc/<path>`.
- Check after every change: `python3 .claude/skills/doc-review/scripts/trace.py` must report `BROKEN LINKS 0` and
  no undefined requirement or watch identifier. The workflow `links.yml` runs the same check and is the required
  check of the repository.

### A change that spans code and documents

An implementation changes code in a code repository and documents here. These are two pull requests that name each
other in their descriptions; the documentation pull request is merged when the code pull request has merged, so that
`main` here never describes code that is not on `main` there (project skill `traced-implementation`).

## Git Workflow

`main` is protected by rulesets and merges go through the merge queue; direct pushes to `main` are not allowed.
Branch, commit, push, open a pull request, wait for the required check `links / links`, answer and resolve every
review comment (the reviewer is `cuioss-review-bot`). Who may merge what is stated in the reference (_From a Branch to `main`_). Commits end with
`Co-Authored-By: plan-marshall <noreply@cuioss.de>`.

## Temporary Files

Never commit working files of a review or an implementation (trace matrices, coverage tables, baselines); they
belong in the session scratchpad.

# AI Engineering from Scratch

A self-paced AI engineering curriculum organized into learning phases, lesson folders, code examples, quizzes, reusable outputs, and a roadmap. It is an educational repository, not a unified software package or a guarantee that every lesson is complete or current.

## Current repository shape

The `main` tree checked on 2026-10-02 contains 20 phase folders and 96 lesson folders across 10 phases. The remaining phase pages currently have no lesson folders in the tree. Lesson materials vary; inspect each lesson for its docs, code, quiz, prerequisites, and dependencies.

Start with the [curriculum index](docs/README.md), [roadmap](ROADMAP.md), and [lesson template](LESSON_TEMPLATE.md). The roadmap records its own progress and time estimates; those are project-maintained planning data, not an independent completeness or duration assessment.

## Explore a lesson

1. Choose a populated phase from the [phase index](docs/README.md).
2. Read that lesson's `docs/en.md` and prerequisites.
3. Inspect the sample code and any quiz or output files.
4. Install only that lesson's dependencies, then run its documented commands in an isolated environment.

There is no root-wide install command or dependency manifest. Do not run a generic `pip install -r requirements.txt` or health check; setup is lesson-specific.

## Repository map

- [`phases/`](phases/): phase pages and lesson folders
- [`ROADMAP.md`](ROADMAP.md): planned subjects, progress marks, and time estimates
- [`LESSON_TEMPLATE.md`](LESSON_TEMPLATE.md): lesson authoring structure
- [`outputs/`](outputs/): reusable prompt/skill/agent/MCP output index; current index arrays are empty
- [`glossary/`](glossary/README.md): terms and AI myths
- [`CONTRIBUTING.md`](CONTRIBUTING.md), [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md), [`FORKING.md`](FORKING.md): contribution and reuse guidance
- [`LICENSE`](LICENSE): MIT license

## Provenance and reuse

The forking guide identifies `rohitg00/ai-engineering-from-scratch` as the upstream repository. Preserve the license and source attribution when adapting or redistributing. See [FORKING.md](FORKING.md).

## Validation and limits

This curriculum has no single root test suite or environment for all examples. File presence does not prove a lesson runs, is complete, or is production-ready. No lesson code or tests were run for this README update. Verify time-sensitive APIs, model names, library versions, and security practices against current primary documentation.

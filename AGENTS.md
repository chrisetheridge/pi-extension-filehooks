# AGENTS.md

## Layout rule

- Keep `src/` runtime-only.
- Pi auto-discovers every `*.ts` file under `src/` as a live extension module.
- Do not place test files, fixtures, or scratch files under `src/`.
- Put tests at the project root or another directory outside `src/`.

## Current convention

- Runtime extension lives in `src/file-hooks/index.ts`.
- Extension docs live in `src/file-hooks/README.md`.
- Tests live at the project root as `file-hooks.test.ts`.

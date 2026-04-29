# AGENTS.md

## Layout rule

- Keep `extensions/` runtime-only.
- Pi auto-discovers every `*.ts` file under `extensions/` as a live extension module.
- Do not place test files, fixtures, or scratch files under `extensions/`.
- Put tests at the project root or another directory outside `extensions/`.

## Current convention

- Runtime extension lives in `extensions/file-hooks/index.ts`.
- Extension docs live in `extensions/file-hooks/README.md`.
- Tests live at the project root as `file-hooks.test.ts`.

# AGENTS.md

## Repo purpose

This repository packages the `pi-file-hooks` Pi extension. The extension watches successful file-mutating tool results and runs configured shell commands for matching paths.

## Layout rules

- Keep `src/` runtime-only.
- Pi auto-discovers every `*.ts` file under `src/` as a live extension module.
- Do not place test files, fixtures, scratch files, or contributor-only docs under `src/`.
- Put tests under `test/`; the current test suite lives in `test/file-hooks.test.ts`.
- Keep extension/user documentation in the root `README.md`.

## Current convention

- Runtime extension entrypoint: `src/file-hooks/index.ts`.
- User-facing extension docs: `README.md`.
- Tests: `test/file-hooks.test.ts`.
- Domain context for agents: `CONTEXT.md`.

## Verification

Run these before claiming implementation work is complete:

- `npm run check`
- `npm test`
- `npm run pack:dry-run`

## Issue tracker

GitHub Issues is the authoritative issue tracker for this repository.

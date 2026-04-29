# pi-file-hooks

Standalone Pi extension package for configurable file hooks.

## What it does

- Runs after file-mutating tool results that include an `input.path`.
- Matches paths against glob patterns from config.
- Executes configured commands and shows hook activity in the Pi UI.

## Layout

- Runtime extension: `extensions/file-hooks/index.ts`
- Extension docs: `extensions/file-hooks/README.md`
- Test file: `file-hooks.test.ts`

## Config

Project-local config lives at `.pi/extensions/file-hooks.json`.
Global config lives at `~/.pi/agent/extensions/file-hooks.json`.

See `extensions/file-hooks/README.md` for the full config schema and template variables.

## Install

```bash
pi install ./ -l
```

## Develop

```bash
npm install
npm run check
npm run test
```

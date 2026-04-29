# pi-file-hooks

Standalone Pi extension package for configurable file hooks.

## What it does

- Runs after file-mutating tool results that include an `input.path`.
- Matches paths against glob patterns from config.
- Executes configured commands and shows hook activity in the Pi UI.

## Config

Project-local config lives at `.pi/extensions/file-hooks.json`.
Global config lives at `~/.pi/agent/extensions/file-hooks.json`.

Example:

```json
{
  "hooks": [
    {
      "name": "cljfmt",
      "match": ["**/*.clj", "**/*.cljc", "**/*.cljs"],
      "command": "bb",
      "args": ["cljfmt-fix", "{path}"]
    }
  ]
}
```

See `src/file-hooks/README.md` for the full config schema and template variables.

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

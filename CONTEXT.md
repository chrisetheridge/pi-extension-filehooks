# pi-file-hooks Context

## Scope

This repository owns the `pi-file-hooks` Pi extension package. The extension reacts to successful Pi `tool_result` events that include `input.path`, matches the path against configured glob rules, and runs matching shell commands.

## Domain Terms

- **hook rule**: One config entry describing the tools, path patterns, command, args, and optional working directory.
- **target path**: The file path from `event.input.path` in a tool result.
- **project config**: `.pi/extensions/file-hooks.json` inside the current project.
- **global config**: `~/.pi/agent/extensions/file-hooks.json`.
- **matching rule**: A hook rule whose tool filter and glob patterns match the current tool result.
- **template variable**: A placeholder such as `{path}` or `{absolutePath}` rendered before command execution.

## Responsibilities

- Load global and project file hook config.
- Merge hook rules, with named project rules replacing earlier named global rules.
- Match successful file-related tool results by tool name and path glob.
- Render template variables in commands, args, and `cwd`.
- Serialize hook command execution to avoid overlapping hook runs.
- Surface hook start/failure status through the Pi UI when available.

## Architectural Rules

- Keep `src/` runtime-only because Pi auto-discovers every `*.ts` file under `src/` as a live extension module.
- Keep tests outside `src/`; current tests live in `test/file-hooks.test.ts`.
- Keep user-facing extension documentation in `README.md`.
- Preserve config precedence: global config loads before project config, and later named rules replace earlier rules with the same name.
- Preserve the default tool filter: when `tools` is omitted, rules apply to `write` and `edit`.
- Avoid hard-coding repo-specific formatter behavior into the extension runtime.
- Treat hook failures as visible warnings/errors for the hook, not as a reason to add unrelated side effects.

## Verification Commands

Run these before claiming implementation work is complete:

```bash
npm run check
npm test
npm run pack:dry-run
```

## Boundaries

- This package is a configurable Pi extension, not a general-purpose task runner.
- Do not add generated files, fixtures, or scratch files under `src/`.
- Do not create per-extension docs under `src/`; keep docs in `README.md` unless a future multi-domain structure justifies a docs directory.
- GitHub Issues is the authoritative issue tracker.

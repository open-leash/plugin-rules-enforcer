# plugin-rules-enforcer

First-party OpenLeash plugin that evaluates agent events against natural-language rules.

This is a first-party OpenLeash plugin repository. The plugin owns its domain logic, prompts, schemas, parsing, and local fallbacks. OpenLeash provides only primitive runtime capabilities such as evaluator LLM calls, plugin-scoped storage, signals, logs, usage records, notifications, and selected host context.

## Source

- `src/manifest.ts` declares events, permissions, settings, ordering, and metadata.
- `src/index.ts` implements the plugin.
- `src/openleash-plugin-runtime.ts` contains tiny local helper types used by this standalone repo.

## Configuration scope

The plugin defines one manifest schema and consumes one request-scoped effective configuration. OpenLeash merges organization defaults, matching organization agent profiles, and permitted user/global or per-agent settings. Organization admins independently choose mandatory installation, employee install freedom, and configuration locking; plugin code does not branch on product mode or user role. The same contract runs in Individual Open Source, personal or organization OpenLeash Cloud, and Private Cloud.

## Development

```bash
npm install
npm run typecheck
```

## Runtime

OpenLeash loads reviewed plugins by manifest metadata and executes their handlers inside the managed plugin runtime.

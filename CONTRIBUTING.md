# Contributing to Orbit

Use Node.js 24.22.2 and pnpm 11.25.0. Windows x64 is the tested desktop platform. The [known limitations](docs/limitations.md) and [project plan](docs/project-plan.md) describe the current scope.

```sh
pnpm install --frozen-lockfile
pnpm typecheck
pnpm test
pnpm build
```

Run `pnpm test:app` for changes to the editor, workbench, or Electron integrations. The Windows desktop tests use Git, PowerShell, and the bundled JS/TS language server. For packaging changes, run `pnpm package` and `pnpm test:package` as well.

For a bug report, include your Orbit version or commit, OS and architecture, steps to reproduce, and what you expected to happen. Reproduce with a minimal workspace that you can share publicly. Remove credentials, private paths, and project data from logs and screenshots.

In your pull request, describe the behavior you changed and the checks you ran. For a larger change such as a new language integration, open an issue first to discuss its scope.

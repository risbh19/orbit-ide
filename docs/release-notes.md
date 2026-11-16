# Orbit 0.1.1

This update adds MIT licensing, updates Electron and the packaging tools, and preserves request order when concurrent saves resolve to the same file. The recovery smoke test waits for a stored session before restarting the app.

Orbit includes a custom piece-table editor with multi-cursor editing, find and replace, highlighting, tabs and split panes. It also provides JS/TS language intelligence, workspace search, Git status, a terminal, and local session recovery.

Windows x64 is the tested platform. Orbit opens valid UTF-8 files up to 1 MiB. See the [known limits](limitations.md) and [performance measurements](performance.md).

## Reproduce on Windows x64

```sh
git checkout <sourceCommit-from-build-info.json>
pnpm install --frozen-lockfile
pnpm typecheck
pnpm test
pnpm build
pnpm test:app
pnpm package
pnpm test:package
pnpm benchmark
pnpm benchmark:desktop
```

Use Node 24.22.2 and pnpm 11.25.0. Keep the complete portable folder together and run `Orbit.exe`. The build metadata in `resources/app/build-info.json` records the source commit, worktree status, Electron version, and lockfile checksum.

Smoke tests exercise the language server, terminal, file execution, Git status, editing, conflicting saves, and restart recovery. The Windows CI workflow runs the source and portable builds and uploads the tested package.

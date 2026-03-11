# Codex VS Code Sandbox Troubleshooting

If VS Code shows:

- `Couldn't set up admin sandbox`
- `Use backup sandbox`
- `error running codex in vscode`

use this quick recovery flow.

## 1) Force backup sandbox mode in the workspace

Create `.vscode/settings.json` and set a non-admin sandbox mode (or disable admin sandbox if available in your extension version).

```json
{
  "codex.sandbox": "backup"
}
```

> Note: Some extension versions use a different setting key. Open **Settings** and search for `codex sandbox` and pick the non-admin/backup option.

## 2) Restart the Codex extension host

1. Run command palette: `Developer: Reload Window`
2. Run: `Codex: Restart Session`

## 3) Validate local runtime dependencies

- Update VS Code and the Codex extension to latest.
- Ensure Docker/containers runtime is running (if your configuration expects it).
- Ensure your shell starts correctly (try opening a fresh integrated terminal).

## 4) Clean cached session state

1. Close VS Code.
2. Reopen VS Code in the same folder.
3. Start a new Codex session in backup mode.

## 5) If it still fails

Capture:

- Output panel logs for `Codex`
- Developer Tools console errors
- OS + VS Code version + extension version

Then file an issue with the exact error string and log snippets.

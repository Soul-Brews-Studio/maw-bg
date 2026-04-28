# maw-bg

> Run long commands in detached tmux; sample output non-destructively.

A `maw-js` community plugin that spawns long-running shell commands inside
detached `tmux` sessions and exposes a small surface for inspecting / managing
them without ever blocking the caller or destroying buffered output.

## Status

**Scaffolded — design review pending.**

This repo currently contains only the plugin skeleton (manifest, stubs, test
shells). Implementation lands after a `/team-agents` 3-agent design review on
the wire contract for each subcommand.

This is **Path A.1**: the first Phase 1 extraction demo for the maw plugin
ecosystem. It is built directly as a community plugin — it does not exist in
the bundled `maw-js` set.

## Planned subcommands

| Command     | Purpose                                                          |
|-------------|------------------------------------------------------------------|
| `bg`        | Spawn a command in a detached tmux session (auto-named)          |
| `bg list`   | List active sessions with status, age, and last-sampled snapshot |
| `bg tail`   | Sample the last N lines non-destructively (no buffer drain)      |
| `bg attach` | Re-attach a TTY to a named session                               |
| `bg kill`   | Terminate a session and clean up resources                       |
| `bg gc`     | Reap stale / dead sessions older than a threshold                |

## Install (when registry ships)

```bash
maw plugin install bg
```

## Capabilities

Declared in `plugin.json`:

- `tmux` — requires a working `tmux` binary on `PATH`

## License

MIT — community-friendly. (Note: `maw-js` core is BUSL-1.1; this plugin
deliberately uses MIT to lower the contribution barrier for community
extensions.)

## Author

[Soul-Brews-Studio](https://github.com/Soul-Brews-Studio) Oracle colony.

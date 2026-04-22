# claude-plugins

An aggregate [Claude Code](https://code.claude.com/docs) marketplace bundling every plugin I've built, so you can install any of them with a single `/plugin marketplace add`.

## Install

```text
/plugin marketplace add https://github.com/thomast8/claude-plugins.git
```

Then install whichever plugins you want:

```text
/plugin install worktree-toolkit@claude-plugins
/plugin install find-reviewer@claude-plugins
/plugin install claude-code-caffeinate@claude-plugins
/plugin install session-title@claude-plugins
```

## What's in the catalog

| Plugin | What it does | Source repo |
|---|---|---|
| **worktree-toolkit** | `/worktree` and `/unworktree` — create git worktrees from PR numbers, branch names, or an interactively-picked PR. Graphite-aware. Bundles `WorktreeCreate`/`WorktreeRemove` hooks. | [claude-worktree-toolkit](https://github.com/thomast8/claude-worktree-toolkit) |
| **find-reviewer** | `/find-reviewer` ranks contributors by load, breadth, and familiarity with the changed files. Auto-detects the current branch's PR. | [claude-find-reviewer](https://github.com/thomast8/claude-find-reviewer) |
| **claude-code-caffeinate** | Keeps your Mac awake only while Claude Code is actively processing. Includes a SwiftBar dashboard showing per-session activity and token usage. | [claude-code-caffeinate](https://github.com/thomast8/claude-code-caffeinate) |
| **session-title** | Auto-renames each session on the first prompt via a Haiku-generated kebab-case summary. One-shot, recursion-safe, fallback to a slugified prompt. | [claude-session-title](https://github.com/thomast8/claude-session-title) |

## Why an aggregate marketplace?

Each plugin lives in its own repo and has its own standalone marketplace, so you can install any of them directly from their source repo if you prefer. The aggregate here just saves users from running `/plugin marketplace add` four times. It re-fetches each plugin's content from its source repo via [`git-subdir`](https://code.claude.com/docs/en/plugin-marketplaces#git-subdirectory-within-a-repo) or [`github`](https://code.claude.com/docs/en/plugin-marketplaces#github-repositories) sources, so updates to the underlying repos flow through without republishing this catalog.

## Updating

```text
/plugin marketplace update claude-plugins
```

Pulls the latest `marketplace.json` and re-resolves each plugin's `source` against the current HEAD of its source repo.

## License

MIT. See [LICENSE](./LICENSE).

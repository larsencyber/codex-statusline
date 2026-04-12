# Codex Statusline

A practical statusline setup for [OpenAI Codex CLI](https://developers.openai.com/codex/) using Codex's built-in TUI footer and terminal title.

![Bash](https://img.shields.io/badge/Bash-4.0%2B-green) ![License](https://img.shields.io/badge/License-MIT-blue)

## Features

- Recommended `status_line` layout for model, directory, context usage, token usage, and rate limits
- Recommended `terminal_title` layout for project, branch, status, thread, and task progress
- Minimal setup: copy the `[tui]` block into `~/.codex/config.toml`
- Reference `recommended-config.toml` you can copy or adapt manually

## Recommended Layout

```toml
[tui]
status_line = ["model-with-reasoning", "current-dir", "context-usage", "used-tokens", "five-hour-limit", "weekly-limit"]
terminal_title = ["project", "git-branch", "status", "thread", "task-progress"]
```

This keeps the most useful live session state visible without trying to emulate Claude Code's custom multi-line shell-rendered statusline.

## Requirements

- Bash 4.0+
- Python 3
- Codex CLI

## Installation

### 1. Clone the repo

```bash
git clone https://github.com/matcluck/codex-statusline.git
cd codex-statusline
```

### 2. Update your Codex config

Copy the `[tui]` block from [`recommended-config.toml`](./recommended-config.toml) into `~/.codex/config.toml`:

```toml
[tui]
status_line = ["model-with-reasoning", "current-dir", "context-usage", "used-tokens", "five-hour-limit", "weekly-limit"]
terminal_title = ["project", "git-branch", "status", "thread", "task-progress"]
```

## Manual Configuration

If you already have a `[tui]` section, merge these two keys into it rather than replacing unrelated settings.

## Files

- `recommended-config.toml` contains the recommended `[tui]` block

## Notes

Codex does not currently use the same external statusline command model as Claude Code. This repo configures Codex's native TUI fields to get a similarly useful footer and terminal title with the features Codex exposes today.

References:

- <https://developers.openai.com/codex/config-basic>
- <https://developers.openai.com/codex/config-reference>

## License

MIT

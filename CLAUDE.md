# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page web project — no build step, no package manager, no test runner. Everything runs directly in the browser.

## Development

Open any `.html` file directly in a browser:
```
start tictactoe.html
```

## Architecture

**`tictactoe.html`** — self-contained single file with inline `<style>` and `<script>`. No external dependencies.

- Game state lives in module-level variables (`board`, `current`, `gameOver`, `scores`, `mode`)
- `play(i)` is the core move handler — updates state, checks win/draw, switches turn
- `aiMove()` uses a priority heuristic (win → block → center → corners → edges); no minimax
- Event delegation on `#board` routes all cell clicks through one listener

## Git & GitHub

After completing any meaningful unit of work, commit and push immediately so progress is never lost and the repo always reflects the latest state.

```
git add <files>
git commit -m "descriptive message"
git push
```

- Commit after each logical change (new feature, bug fix, config update, etc.)
- Do not batch unrelated changes into one commit
- Push immediately after committing — do not leave commits unpushed

Remote: https://github.com/newbornspec/claude-code-test

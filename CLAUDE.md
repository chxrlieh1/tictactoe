# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the project

Open `index.html` directly in a browser — no build step, server, or dependencies required:

```
open index.html
```

## Architecture

The entire project is a single file: `index.html`. It contains HTML, CSS, and JavaScript inline with no external dependencies.

**Game state** lives in three module-level variables: `board` (9-element array of `''|'X'|'O'`), `current` (whose turn), and `over` (boolean).

**Key functions:**
- `init()` — resets board state, clears cell DOM, removes any confetti canvas
- `checkWin()` — iterates `WINS` (the 8 winning triplets) and returns the winning indices or `null`
- `celebrate()` — spawns a `<canvas class="confetti-canvas">` overlay, animates 100 particles with `requestAnimationFrame`, and self-removes when done

**Piece placement** uses `cell.innerHTML = '<span class="symbol">...</span>'` so the `pop-in` keyframe animation targets the inner span, not the cell itself (which has its own hover transform).

## Git workflow

Commit after every meaningful change and push to GitHub (`chxrlieh1/tictactoe`). Commit messages should be imperative, describe what changed and why, and include the co-author trailer:

```
Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
```

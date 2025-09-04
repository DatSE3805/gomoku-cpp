# gomoku.cpp
*Console Gomoku (15×15) in C++ with strict five-in-a-row rules and replay.*

Turn-based **Gomoku (Five-in-a-Row)** on a 15×15 board, built in C++17. Implements standard rules with two assignment-specific constraints: **no overlines** (6+ doesn’t win) and **two-headed blocks** (blocked at both ends) don’t count as a win. Includes a **history replay** mode.

## Features
- **Board & input:** 15×15 grid; moves entered as `RowColumn` (e.g., `12i`, `5o`).
- **Win logic:** Detects five in a row (H/V/diag); rejects **overline** and **blocked-at-both-ends** sequences.
- **Modes:**
  - Play Game (turn-based X/O)
  - History Replay (`p`/`n`/`s`)
  - Exit
- **Compact I/O:** Minimal console output for easy testing.

## How it works
- `makeMove(board, size, playerMove, isFirstPlayerTurn)` — validate notation/range/emptiness, then write move.
- `hasWon(board, size, isFirstPlayerTurn)` — scan 4 directions; enforce no-overline + two-headed-block rules.
- `displayHistory(history, numOfMoves)` — step through a recorded game (`p` = previous, `n` = next, `s` = stop).
- Entry menu: **Play Game / History / Exit** with input validation loops.

## Quick start
> Requires a C++17 toolchain.

```bash
g++ -O2 -std=c++17 -o gomoku gomoku.cpp
./gomoku
```

Welcome to Gomoku!
1. Play Game
2. History
3. Exit

Please select mode [1/2/3]:

Previous move/Next move/Stop [p/n/s]:

# Project structure
```text
gomoku/
├─ gomoku.cpp
└─ Gomoku.pdf

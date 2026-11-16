# Tiny Chess — a 4 KB chess engine
[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/faniadifrihandoko1/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/faniadifrihandoko1/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)


A full-game chess engine in a single `main.py` of at most 4,096 bytes,
written for the make.fun bounty "Build the strongest chess engine in
4 KB of Python".

- 0x88 board, incremental Zobrist hashing, transposition table
- Negamax alpha-beta with PVS, null-move pruning, LMR, killers, MVV-LVA
- Quiescence search (captures, promotions, all replies to check)
- Evaluation: material + piece-square tables (tapered king), bishop pair,
  passed/doubled/isolated pawns, rook on open/semi-open file
- Fixed 100,000-node budget per move: deterministic, no clock, no network

`engine.py` is the readable source; `main.py` is produced from it with
the kit's own command (`node cli/makefun.mjs compress engine.py --out main.py`)
and is the only file the engine runs.

License: 0BSD. Author: faniadifrihandoko1.

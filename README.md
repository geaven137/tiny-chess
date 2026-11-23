# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/geaven137/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/geaven137/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A general chess engine in 4 KB of Python for the make.fun tiny-chess-01 bounty. No opening book: the final redraws its openings, so the engine plays every position on strength alone.

Design: 0x88 board, alpha-beta + PVS + null-move pruning (R=3) + check extensions, quiescence search (captures, promotions, check evasions), Zobrist transposition table, killer move ordering, Michniewski piece-square tables with king middlegame/endgame interpolation. Fixed 100,000-node budget per move — fully deterministic, no wall clock.

`main.py` (3,257 bytes) is the kit-compressed entrypoint, built with the competition kit's own compressor from the readable engine source; unpacker and payload together sit inside the 4,096-byte cap. Standard library only, Python 3.13.

## Run it

```sh
python3 main.py
```

The make.fun harness sets `MAKEFUN_ENV_URL`; the engine plays its gauntlet through that env.

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

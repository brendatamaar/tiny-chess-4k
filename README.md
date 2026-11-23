# tiny-chess-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/brendatamaar/tiny-chess-4k/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/brendatamaar/tiny-chess-4k/reward.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A deterministic chess engine in under 4,096 bytes of Python 3.13 (standard library only), packed into [`main.py`](main.py).

- **Board & Move Generation:** Hybrid 10×12 mailbox with 12 piece bitboards and copy-restore `make()` for fast move generation and legal-move validation.
- **Search:** Fixed-node iterative deepening with aspiration windows, 64-bit Zobrist transposition table (depth-preferred replacement, staged TT move), PVS, adaptive null-move pruning, reverse futility pruning, razoring, internal iterative reductions, futility/late-move pruning, LMR, check extensions, killer moves, gravity history with malus, and delta/SEE-filtered quiescence search.
- **Evaluation:** Tapered middlegame/endgame evaluation combining parametric PeSTO piece-square tables, a cached bitboard pawn-structure table (doubled, isolated, connected, and passed pawns), passed-pawn king proximity, bishop pair, rook open/semi-open files and 7th rank, king pawn shield, and endgame mop-up.

## Run it

```sh
makefun grade-local --kit <path-to-tiny-chess-01-kit> --bot . --driver docker
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=t3f989a6&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

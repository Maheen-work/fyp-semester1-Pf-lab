# fyp-semester1-Pf-lab
Console-based escape room game in C. Solve randomized logic and cipher puzzles (Caesar, XOR, number locks) room by room, with save/resume and a leaderboard.
# Escape Room Puzzle Engine

A console-based escape room game written in C. Solve a different logic or code-breaking puzzle in each room to unlock the next door. Puzzles are generated at runtime, so no two playthroughs are the same.

Built for the Programming Fundamentals course project at FAST-NUCES, Karachi Campus.

## Features

- **Multi-room progression**: solve Room N to unlock Room N+1
- **Randomized puzzles**: numeric locks, Caesar-shift clues, XOR-encoded clues, number sequences
- **Save / Resume**: progress is written to a file after every move, so you can quit and continue later
- **Inventory**: some rooms give a key item that a later room requires
- **Hints**: available at a move/time penalty
- **Leaderboard**: logs completion time and moves per player, shown sorted
- **Difficulty levels**: Easy / Medium / Hard change puzzle ranges and number of rooms

## Getting Started

### Requirements

- GCC (or any standard C compiler)
- Windows (tested), should also work on Linux/macOS

### Build

```bash
gcc main.c flow.c puzzles.c files.c -o escape
```

### Run

```bash
./escape        # Linux / macOS
escape.exe      # Windows
```

## How to Play

1. Pick **New Game** or **Resume** from the main menu.
2. Read the clue in each room and type your answer.
3. Use a hint if you are stuck (it adds a penalty).
4. Escape all rooms to land on the leaderboard.

Example clue:

```
Room 2: The wall reads "KHOOR". The old note says: shift of 3.
> hello
Correct! The door unlocks.
```

## Project Structure

```
.
├── game.h          # shared structs, constants, function declarations
├── main.c          # entry point
├── flow.c          # menu, room progression, inventory
├── puzzles.c       # puzzle generators, answer checking, hints
├── files.c         # save/load, leaderboard
├── rooms.txt       # room definitions
├── save.txt        # saved game state (generated)
└── leaderboard.txt # completed runs (generated)
```

## Data Files

All storage uses plain `.txt` flat files:

| File | Purpose |
|------|---------|
| `rooms.txt` | Room definitions (type, clue, hint, rewards) |
| `save.txt` | Current room, inventory, moves, time |
| `leaderboard.txt` | Player name, moves, time, difficulty |

## Team

| Member | Module |
|--------|--------|
| Maheen Shafiq | TBD |
| Faaleha Haq | TBD |
| (Third member) | TBD |

Modules: game flow (`flow.c`), puzzles (`puzzles.c`), file handling (`files.c`).



## License

Academic project. Not licensed for redistribution.

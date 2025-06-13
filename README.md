# Tic-Tac-Toe

A classic Tic-Tac-Toe game implemented in C with support for human vs human, human vs computer, and computer vs computer gameplay modes.

## Features

- **Multiple Game Modes**: Play against another human, against the computer, or watch two computers play
- **Intelligent AI**: The computer uses strategic gameplay including center control and win/block detection
- **Colorful Display**: Uses ANSI color codes for an enhanced visual experience
- **Input Validation**: Handles invalid moves and out-of-range inputs gracefully

## Game Modes

- **0 Players**: Computer vs Computer (watch two AIs battle it out)
- **1 Player**: Human vs Computer (you can go first or second, determined randomly)
- **2 Players**: Human vs Human (classic two-player mode)

## How to Play

### Compilation
```bash
gcc -o tictactoe main.c
```

### Running the Game
```bash
./tictactoe
```

### Gameplay
1. Choose the number of players (0, 1, or 2)
2. The game board shows numbered squares (1-9) for available moves
3. Players take turns selecting squares by entering the corresponding number
4. X always goes first, O goes second
5. Enter `0` to quit the game at any time

### Board Layout
```
 1   2   3 
 4   5   6 
 7   8   9 
```

## Game Logic

### Computer AI Strategy
The computer AI follows this decision-making process:
1. **Opening Move**: Takes the center (square 5) if available, or square 1 on the second move
2. **Win Detection**: Looks for opportunities to complete three in a row
3. **Block Detection**: Prevents the opponent from winning by blocking their potential winning moves
4. **Random Move**: If no strategic move is available, selects a random empty square

### Win Conditions
The game checks for wins in all possible lines:
- Horizontal: rows 1-3, 4-6, 7-9
- Vertical: columns 1-4-7, 2-5-8, 3-6-9
- Diagonal: 1-5-9, 3-5-7

## Visual Features

- **Color-coded pieces**: X appears in red, O appears in blue
- **Alternating background**: Checkerboard pattern for better visibility
- **Clear winner announcement**: Displays the final board state and winner

## Code Structure

- `showgrid()`: Displays the current board state with colors
- `winner()`: Checks for win conditions and announces the winner
- `prompt()`: Handles human player input and validation
- `three()`: Strategic function that detects two-in-a-row situations
- `computer()`: AI decision-making logic
- `main()`: Game loop and initialization

## Requirements

- C compiler (GCC recommended)
- Terminal with ANSI color support for best visual experience

## Example Output

```
Tic-Tac-Toe
Number of players (0, 1, 2): 1
you go first

 1   2   3 
 4   5   6 
 7   8   9 

X's turn: Pick a square, 0 to quit: 5
The computer moves to square 1
 O   2   3 
 4   X   6 
 7   8   9 
```

## Notes

- The game uses ANSI escape codes for colors, which work in most modern terminals
- Grid positions are internally represented as 0-8 but displayed to users as 1-9
- The computer's difficulty is moderate - it will block obvious wins but may not always play optimally
# Tic Tac Toe

A console-based implementation of the classic Tic Tac Toe game written in Python. Features a two-player game with a clean terminal interface and replay functionality.

## Features

- **Two-player gameplay**: Players take turns as X and O
- **Random turn selection**: First player is chosen randomly each game
- **Input validation**: Prevents invalid moves and positions
- **Win detection**: Checks for all possible winning combinations
- **Draw detection**: Automatically detects when the board is full
- **Replay functionality**: Option to play multiple games in sequence
- **Clean terminal interface**: Cross-platform screen clearing

## Requirements

- Python 3.x
- Works on Windows (uses `cls` command for screen clearing)

## Installation

1. Clone or download the script
2. Ensure Python 3.x is installed on your system
3. No additional dependencies required

## Usage

Run the script from your terminal:

```bash
python tic_tac_toe.py
```

### Game Flow

1. **Marker Selection**: Player 1 chooses to be X or O
2. **Turn Order**: System randomly determines who goes first
3. **Gameplay**: Players alternate turns selecting positions 1-9
4. **Position Layout**: 
   ```
   7 | 8 | 9
   -----------
   4 | 5 | 6
   -----------
   1 | 2 | 3
   ```
5. **Game End**: Win, draw, or replay option

### Example Session

```
Welcome to Tic Tac Toe!
Player 1: Do you want to be X or O? X
Player 2 will go first.
Are you ready to play? Enter Yes or No. yes

   |   |  
-----------
   |   |  
-----------
   |   |  

Choose your next position: (1-9) 5
```

## Code Architecture

### Core Functions

- **`display_board(board)`**: Renders the current game state with ASCII art
- **`player_input()`**: Handles marker selection (X/O) with input validation
- **`place_marker(board, marker, position)`**: Updates board state
- **`win_check(board, mark)`**: Evaluates all 8 winning combinations
- **`choose_first()`**: Random player selection using `random.randint()`
- **`space_check(board, position)`**: Validates move legality
- **`full_board_check(board)`**: Detects draw conditions
- **`player_choice(board)`**: Input validation for position selection
- **`replay()`**: Game continuation logic

### Win Conditions

The `win_check()` function evaluates 8 possible winning combinations:
- 3 horizontal rows
- 3 vertical columns  
- 2 diagonal lines

## Technical Notes

### Cross-Platform Compatibility
- Currently uses `os.system('cls')` for Windows screen clearing
- For cross-platform support, consider implementing OS detection:
  ```python
  def clear():
      os.system('cls' if os.name == 'nt' else 'clear')
  ```

### Input Validation
- Position input is validated to ensure it's within range 1-9
- Space availability is checked before allowing moves
- Marker selection is validated to accept only 'X' or 'O'

### Game State Management
- Board state is maintained in the main game loop
- Turn alternation is handled through string comparison
- Game continuation is controlled by boolean flags

## Potential Improvements

1. **AI Implementation**: Add single-player mode with computer opponent
2. **Enhanced UI**: Implement colorized output or GUI interface
3. **Score Tracking**: Maintain win/loss statistics across games
4. **Configuration**: Allow board size customization (NxN grids)
5. **Code Refactoring**: Implement object-oriented design with Game/Player classes
6. **Error Handling**: Add try-catch blocks for robust input handling


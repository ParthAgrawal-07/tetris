# Tetris Game 🎮

## Created by:
Group **404**

1. Parth Agrawal
2. Abhijeet Kujur
3. Heer Bhanushali
4. Harsh Asnani

## Introduction
The Tetris Game is a classic arcade game where the player controls falling Tetrominoes to create complete lines, which are then cleared from the playing field. The challenge is to keep the screen from filling up with Tetrominoes. This Tetris game is made using basic C++ codes and some concepts of Object Oriented Programming.

## Objective
The goal of the game is to manipulate the falling Tetrominoes to create complete lines without any gaps. The more lines you clear, the higher your score. If the Tetrominoes stack up to the top of the playing field, the game is over. 🎈

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/tetris.git
   cd tetris
   ```
2. Install dependencies (if any):
   ```sh
   `conio.h` library should be there
   `windows.h` library should be there
   ```

## Requirements
- Operating System: Windows as we have included `windows.h` library it would run in windows terminal
- Compiler: C++ Compiler (GCC MinGW or MSVC)

## Platform
- Windows

## Compiler
- GCC (MinGW) (for Windows)

## Libraries

- `windows.h` for 'cls' and sleep function
- `iostream.h` for basic commands
- `conio.h` for _kbhit and _getch
- `cstdlib` for rand and srand
- `ctime` for time
- `vector` for vector
- `fstream` for file handling
- `unordered_map` for high score management
- `algorithm` for sorting

## How to Compile and Run

### On Windows
#### Using GCC (MinGW):
```
g++ main.cpp -o tetris
```
```
./tetris
```

## Display of the Game
- It's a simple Tetris game with a straightforward UI/UX, making it easy to understand and play. 🕹️

## Key Features
- Classic Tetris mechanics 🧩
- Tetromino rotation and movement 🔄
- Line clearing and scoring 🏆
- High score tracking and leaderboard 🏅
- Adjustable difficulty levels 🌟
- Sound effects for row clearing 🔊

## How to Play

1. Use the following keys to control the Tetrominoes:
   - `A` - Move left
   - `D` - Move right
   - `S` - Speed up descent
   - `W` - Rotate the piece
   - `Space` - Hard drop
   - `ESC` - Quit the game
2. The goal is to create complete lines without gaps to clear them and increase your score.
3. Avoid stacking the Tetrominoes to the top of the playing field.

## Data Structures Used
### 1. Struct: Tetromino

The `Tetromino` struct is responsible for handling the Tetromino's shape, position, and color.

#### Attributes:

- `vector<pair<int, int>> shape;` - Stores the shape of the Tetromino.
- `int x, y;` - Stores the current position of the Tetromino.
- `int color;` - Stores the color of the Tetromino.

### 2. Class: Grid

The `Grid` class is responsible for managing the game grid, including Tetromino placement and line clearing.

#### Attributes:

- `vector<vector<char>> grid;` - Stores the game grid.
- `vector<vector<int>> colorGrid;` - Stores the color of each cell in the grid.

#### Methods:

- **`Grid();`**
  - Constructor that initializes the game grid with empty cells.

- **`void drawGrid() const;`**
  - Clears the screen and redraws the game grid.
  - Displays the Tetrominoes, walls, and the current score.

- **`bool isCollision(int dx, int dy) const;`**
  - Checks if moving the Tetromino by `dx` and `dy` would result in a collision.
  - Returns `true` if a collision is detected, indicating the Tetromino cannot move in that direction.

- **`void clearFullRows();`**
  - Clears full rows from the grid and shifts the rows above down.
  - Increases the score and plays a sound effect when a row is cleared.

- **`void lockPiece();`**
  - Locks the current Tetromino in place on the grid.
  - Updates the high score if the current score is higher.

### 3. Class: Game

The `Game` class handles the overall game logic, rendering, and user interaction.

#### Attributes:

- `Tetromino currentPiece;` - The current falling Tetromino.
- `Tetromino nextPiece;` - The next Tetromino to fall.
- `Grid grid;` - The game grid.
- `int score;` - The player's current score.
- `int linesCleared;` - The number of lines cleared.
- `int level;` - The current difficulty level.
- `unordered_map<string, pair<int, string>> userHighScores;` - Stores the high scores for each user.
- `vector<pair<string, pair<int, string>>> leaderboard;` - Stores the global leaderboard.
- `string currentUserName;` - The name of the current user.
- `string currentUserId;` - The ID of the current user.

#### Methods:

- **`Game();`**
  - Constructor that initializes the game and sets up the random number generator using `srand(time(0))`.

- **`void startMenu();`**
  - Displays the start menu and prompts the user to enter their name and ID.
  - Shows the high score for the current user and the global leaderboard.

- **`void gameLoop();`**
  - The main game loop that continuously runs:
    - Calls `drawGrid()` to render the game state.
    - Captures user input and updates the game mechanics.
    - Adjusts the game difficulty based on the score.
    - Ends the game if the player loses and prompts for replay.

- **`void loadHighScores();`**
  - Loads the high scores from a file.

- **`void saveHighScores();`**
  - Saves the high scores to a file.

- **`void displayHighScore() const;`**
  - Displays the high score for the current user.

- **`void displayLeaderboard() const;`**
  - Displays the global leaderboard.

### 4. Class: GameState

The `GameState` class manages the state of the game, including tracking the score and determining if the game is over.

#### Attributes:

- `bool gameOver;` - A flag that indicates whether the game is over.
- `int score;` - Stores the player's current score.

#### Methods:

- **`GameState();`**
  - Constructor that initializes the game state.
  - Sets `gameOver` to `false` and `score` to `0` at the start of the game.

## Other Data Structures Used
- Data structures such as arrays, 2D arrays for grid making, vectors for Tetromino movement are used. For random value generation, we have used `rand` and `srand` functions.
- Functions like `_kbhit` are used to ensure that a key is pressed on the keyboard.
- `_getch` pauses the output console until a key is pressed.

## Future Enhancements

- Implementing different difficulty levels (this can be done by reducing the sleep timer to increase the speed of the Tetrominoes). 🌟
- Adding more sound effects and animations (can be done using a beep function). 🔊

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. 📜

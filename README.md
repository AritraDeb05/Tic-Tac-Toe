# N×N Tic-Tac-Toe

A dynamic, browser-based Tic-Tac-Toe game built in a single `main.html` file using HTML, CSS, and JavaScript. Play on grid sizes from 3×3 up to 10×10, with the win condition automatically adjusted to keep the game fair and challenging.

## Features

- Variable board sizes: choose any grid from 3×3 to 10×10 using a dropdown selector.
- Automatic win rules based on grid size:
  - 3 in a row to win for 3×3, 4×4, and 5×5 boards.
  - 4 in a row to win for 6×6, 7×7, 8×8, 9×9, and 10×10 boards.
- Two-player local mode (Player X vs Player O) with clear turn indication.
- Visual win highlight: winning cells are animated and colored to emphasize the winning line.
- Responsive board sizing: cell size and font automatically adjust so larger grids still fit comfortably on screen.
- “New Game” button to instantly reset the board and start over with the current grid size.
- All logic, styles, and markup bundled into a single `main.html` file—no external dependencies.

## Tech Stack

- HTML5 for structure and UI layout.
- CSS3 (inline `<style>` block) for styling, animations, and responsive grid design.
- Vanilla JavaScript (inline `<script>` block) for game logic, dynamic board generation, and win detection.

## Getting Started

### Prerequisites

- Any modern web browser (Chrome, Firefox, Edge, etc.).

No server, build tools, or package manager are required; everything runs from the single HTML file.

### Installation

1. Clone or download this repository.
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```

2. Make sure `main.html` is in the project root.

### Running the Game

1. Open the `main.html` file in your browser:
   - Double-click `main.html`, or
   - Right-click → “Open with” → choose your browser.

2. The N×N Tic-Tac-Toe interface will load and you can start playing immediately.

## How It Works

### Board Size and Win Condition

- The current grid size `N` is selected from the “Grid Size” dropdown (3 to 10).
- The code uses this value to:
  - Generate an N × N grid of clickable cells.
  - Set the required number of marks in a row to win (`winNeed`):
    - 3 for N ≤ 5.
    - 4 for N > 5.
- The current win condition (“Win condition: X in a row”) is shown dynamically above the board.

### Gameplay Flow

- Players X and O take turns clicking empty cells. Each click:
  - Places the current player’s mark (`X` or `O`) in that cell.
  - Locks the cell (disabled so it cannot be played again).
  - Triggers a win check based on the last move.

- The win check scans horizontally, vertically, and both diagonal directions from the last move, counting contiguous marks for the current player.
- If the number of contiguous marks in any direction is at least `winNeed`, those cells are returned as the winning line and visually highlighted.
- If the board is full and no player meets the win condition, the game declares a draw.

Status messages at the top indicate whose turn it is, who won, or if the game ended in a draw, with different colors for X’s turn, O’s turn, wins, and draws.

### UI and Visual Design

- Central “Game Container” card with title, subtitle, controls, board, and legend.
- Grid is rendered using CSS `display: grid` and `grid-template-columns` to adapt to the chosen size.
- Hover and click animations give responsive feedback on each move.
- Winning cells animate and change background color for a brief “pulse” effect.

## File Structure

This project intentionally keeps everything in one file for simplicity and easy sharing.

```text
.
└─ main.html   # Contains HTML markup, CSS styles, and JavaScript game logic
```

## Possible Extensions

- Add an AI opponent (e.g., random moves, heuristics, or minimax for smaller boards).
- Allow custom win length selection (user chooses how many in a row are needed, independent of N).
- Add sound effects and more advanced animations for moves and wins.
- Track score across multiple rounds (wins for X, wins for O, draws).






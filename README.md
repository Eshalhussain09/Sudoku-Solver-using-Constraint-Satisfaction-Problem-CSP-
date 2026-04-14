# Sudoku-Solver-using-Constraint-Satisfaction-Problem-CSP-
# Sudoku Solver using CSP (AC-3 + Backtracking + Forward Checking)

## Overview
This project implements a Sudoku solver using the **Constraint Satisfaction Problem (CSP)** approach. The solver combines **Arc Consistency (AC-3)**, **Backtracking Search**, **Forward Checking**, and the **Minimum Remaining Values (MRV)** heuristic to efficiently solve Sudoku puzzles of varying difficulty levels.

---

## Features
- Solves standard 9×9 Sudoku puzzles  
- Uses AC-3 algorithm for constraint propagation  
- Implements MRV heuristic for efficient variable selection  
- Applies forward checking to reduce unnecessary search  
- Tracks performance using:
  - Backtracking calls  
  - Backtracking failures  
- Supports multiple difficulty levels (easy, medium, hard, evil)  

---

## Project Structure
```
.
├── solver.py
├── easy.txt
├── medium.txt
├── hard.txt
├── evil.txt
└── README.md

```

---

## Input Format
- Each Sudoku puzzle is stored in a `.txt` file  
- Each line represents a row of the grid  
- Use digits `1–9` for filled cells  
- Use `0` for empty cells  

### Example
```

530070000
600195000
098000060
800060003
400803001
700020006
060000280
000419005
000080079

```

---

## How It Works

### 1. Domain Initialization
- Each cell is treated as a variable  
- Domains:
  - Filled cell → single value  
  - Empty cell → values from 1 to 9  

### 2. Constraint Propagation (AC-3)
- Removes inconsistent values from domains  
- Ensures no conflicts between neighboring cells  

### 3. Variable Selection (MRV)
- Selects the unassigned variable with the smallest domain  
- Reduces the search space  

### 4. Forward Checking
- Removes assigned values from neighboring domains  
- Detects failures early  

### 5. Backtracking Search
- Recursively assigns values  
- Backtracks when constraints are violated  

---

## How to Run

1. Install Python (3.x)  
2. Place puzzle files in the same directory as the script  
3. Run the program:

```

python solver.py

```

---

## Output
For each puzzle, the program displays:
- Initial Sudoku board  
- Solved Sudoku board  
- Performance statistics:
  - Number of backtracking calls  
  - Number of backtracking failures  

---

## Example Output
```

==========================================
File: easy.txt
==============

Puzzle:
5 3 0 | 0 7 0 | 0 0 0
...

Solution:
5 3 4 | 6 7 8 | 9 1 2
...

BACKTRACK calls   : 45
BACKTRACK failures: 3

```

---

## Performance Analysis
- Easy puzzles: minimal backtracking  
- Medium puzzles: moderate computation  
- Hard puzzles: higher search effort  
- Evil puzzles: significant backtracking and constraint propagation  

---

## Technologies Used
- Python  
- Constraint Satisfaction Problem (CSP) techniques  

---

## Future Improvements
- Add graphical user interface (GUI)  
- Support larger grids (e.g., 16×16)  
- Implement additional heuristics (e.g., Least Constraining Value)  
- Optimize performance further  

---

## License
This project is for educational purposes.
```

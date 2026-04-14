# Sudoku Solver CSP

A high-performance Sudoku solver implemented as a **Constraint Satisfaction Problem (CSP)**. This project demonstrates the application of classic Artificial Intelligence techniques to solve puzzles ranging from "Easy" to "Very Hard" with minimal backtracking.

## 🚀 Features

This solver utilizes several optimization techniques to navigate the $9 \times 9$ search space efficiently:

  * **AC-3 (Arc Consistency Algorithm):** A pre-processing step that prunes the search space by ensuring every variable's domain is consistent with its neighbors' constraints before backtracking even begins.
  * **Backtracking Search:** A depth-first search (DFS) algorithm used to find a complete and consistent assignment.
  * **MRV (Minimum Remaining Values) Heuristic:** For variable selection, the solver chooses the cell with the fewest legal values left in its domain, significantly reducing the branching factor.
  * **Forward Checking:** During the search, the solver looks ahead to neighboring cells and prunes their domains, allowing it to detect failures earlier and backtrack sooner.

-----

## 🛠️ How It Works

The solver treats Sudoku as a CSP with:

1.  **Variables ($X$):** 81 cells on the board.
2.  **Domains ($D$):** Integers $\{1, 2, \dots, 9\}$.
3.  **Constraints ($C$):** All-different constraints for every row, column, and $3 \times 3$ sub-grid.

### Performance Metrics

The script tracks and outputs:

  * **Backtrack Calls:** Total nodes explored in the search tree.
  * **Backtrack Failures:** Number of times the solver hit a dead end and reverted.
  * **Execution Time:** Total time taken to reach a solution.

-----

## 💻 Getting Started

### Prerequisites

  * Python 3.x

### Installation

Clone the repository to your local machine:

```bash
git clone https://github.com/Roay-Abdullah/Sudoku-Solver-CSP.git
cd Sudoku-Solver-CSP
```

### Usage

Run the script directly to see the solver handle the built-in test cases:

```bash
python sodukoSolverCSP.py
```

To solve your own board, modify the `boards` dictionary in the script. Boards are represented as a single string of 81 characters, where `0` represents an empty cell.

-----

## 📊 Example Output

```text
---------- Solving Hard Board ----------
1 8 2 | 3 4 6 | 9 5 7
4 6 5 | 7 8 9 | 2 3 1
3 7 9 | 5 2 1 | 8 6 4
------+-------+------
8 1 3 | 6 5 7 | 4 9 2
5 4 7 | 9 1 2 | 3 8 6
9 2 6 | 4 3 8 | 5 7 1
------+-------+------
7 5 8 | 2 9 3 | 6 1 4
6 9 4 | 8 7 5 | 1 2 3
2 3 1 | 1 6 4 | 7 4 5

Backtrack Calls: 81 
Backtrack Failures: 0 
Execution Time: 0.0042 seconds
```

-----

## 📂 Project Structure

| File | Description |
| :--- | :--- |
| `SudokuCSP` | The core class containing the CSP logic and solvers. |
| `generateConstraints` | Builds the adjacency list for rows, columns, and boxes. |
| `ac3` | Implements the Arc Consistency algorithm. |
| `backtrack` | The recursive search function with MRV and Forward Checking. |
| `printPrettySudoku` | A helper function for grid visualization. |

-----

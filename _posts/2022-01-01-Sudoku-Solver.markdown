---
layout: post
title:  "Sudoku Game Solver (Language: Python)"
date:   2024-10-20 10:36:35 -0400
categories: jekyll update
---
# Description of Game/Rules
Sudoku is a logic-based puzzle game played on a 9x9 grid divided into nine 3x3 subgrids, or “boxes.” Each row, column, and box must contain all numbers from 1 to 9 without repetition. The puzzle begins with some cells pre-filled with numbers, called "givens," which serve as clues to help players complete the grid. The challenge of Sudoku lies in deducing the values of the empty cells based on the constraints imposed by the existing numbers.

The objective of Sudoku is to fill every empty cell so that each number from 1 to 9 appears only once in each row, column, and box. Players must use logic and process of elimination rather than guesswork, analyzing the grid to deduce where each number can or cannot go. Sudoku puzzles come in various levels of difficulty, ranging from easy, which require straightforward deductions, to hard or expert levels, which may need advanced strategies to solve. An example board is shown below.

<p align="center">
  <img src="/assets/Sudoku_Image.png" alt="Image description" width="300">
</p>

# Notable aspects of the game environment
This game setup can be represented as a contraint satisfaction problem, meaning we can set up the environment with formal declerations of what is allowed and what is not allowed (contraints) and implement a simple general purpose algorithm to follow these rules until it arrives at a solution. Note that in these types of games, there is only one solution to the problem, therefore we do not have to consider if the solution is optimal, just simply whether it is correct.

More formally, a CSP consists of:
- Finite set of variables X<sub>1</sub>, X<sub>2</sub>, ..., X<sub></sub>
- Nonempty domain of possible values for each variable D<sub>1</sub>, D<sub>2</sub>, ...,D<sub>n</sub> where D<sub>i</sub> = {v<sub>1</sub>, ..., v<sub>k</sub>}
- Finite set of constraints C<sub>1</sub>, C<sub>2</sub>, ..., C<sub>m</sub>
    - Each constraint C<sub>i</sub> limits the values that variables can take, e.g., X<sub>1</sub> ≠ X<sub>2</sub> 
    - A state is defined as an assignment of values to some or all variables.

# Algorithm used to solve Sudoku
...
``` python 
function AC-3(csp) # return the CSP, possibly with reduced domains
    inputs: csp, a binary csp with variables {X1, X2, ..., Xn}
    local variables: queue, a queue of arcs initially the arcs in csp
    while queue is not empty do:
        (Xi, Xj) = queue.pop()
        if REMOVE-INCONSISTENT-VALUES(Xi, Xj):
            for each Xk in NEIGHBORS[Xi] – {Xj}:
                add (Xk, Xi) to queue

function REMOVE-INCONSISTENT-VALUES(Xi, Xj) # return true iff we remove a value
    removed = false
    for each x in DOMAIN[Xi]:
        if no value y in DOMAIN[Xj] allows (x,y) to satisfythe constraints between Xi and Xj:
            delete x from DOMAIN[Xi]
            rmmoved = True
    return removed
        
```

# Implementation
Due to the nature of UPenn's Academic Integrity Policy, I am unable to publicly share the code I developed or go in depth about the specifics of any type of implementation. I would be happy to share my project privately to any recruiters or engineers that would like to analyse my work in detail. 



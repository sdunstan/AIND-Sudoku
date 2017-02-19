# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propagation is the idea of reducing the domain of a variable using inference. 
In a constraint satisfaction problem such as Sodoku, we can use the constraints on one variable to reduce the domain of another. 
Naked twins allows us to use inference to reduce the domain of non-naked twins in the same units 
because we know that the naked twin boxes domain has been reduced to only two values. Therefore, 
other non-naked twin boxes in the same unit cannot contain these values.

The naked twins strategy reduces the search space to allow a constraint satisfaction problem like Sodoku to be solved faster.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonal soduku extends the constraints of soduku to the game diagonals. This means that boxes in the corners belong to
a diagonal unit in addition to the usual row, column, and 3x3 square units. Boxes in the center unit belong to both diagonal
units in addition to the usual ones.

In order to see how we can use constraint propagation to solve diagonal sodoku, we must first make the assumption that the
algorithms we are using for constraint propagation are unit shape/type agnostic. In other words, the concept of a unit is
abstract to our naked twin, elimination, and only-choice algorithms.

Assuming our algorithms are unit agnostic, **we only need to introduce the additional diagonal units**. In order for the
sudoku to be solved, each box must be consistent with its constraints across all units. Elimination, for example, 
reduces the domain of other units that a box belongs to when we know the value for that box -- that constraint propagation 
algorithm does not change by adding diagonal units. So a value of 9 in box A1, eliminates 9 from all other boxes of the 
upper left 3x3 square, row A, column 1, and the diagional that intercets A1.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
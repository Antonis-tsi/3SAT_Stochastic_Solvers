# 3-SAT Stochastic Local Search Solvers

A C++ implementation of various Stochastic Local Search (SLS) algorithms for solving the Boolean Satisfiability Problem (3-SAT). 

## Overview
This project generates random 3-SAT problems with customizable parameters and evaluates the performance of different local search algorithms in finding a satisfying assignment. 

The repository includes a custom SAT generator and four solving algorithms:
* **GSAT**: A standard greedy local search algorithm.
* **GSAT with Random Walk (GSAT-RW)**: Introduces random noise to escape local optima.
* **WalkSAT**: A solver that focuses on picking variables from unsatisfied clauses.
* **Semi-Greedy WalkSAT**: A variant of WalkSAT that uses a semi-greedy approach for the initial variable assignment.

## Project Structure
* `main.cpp`: The entry point that orchestrates the problem generation and testing of all algorithms.
* `sat_generator.cpp` & `sat_generator.h`: Generates 3-SAT formulas based on the specified number of variables, clauses, and negative literal probability.
* `solvers_help_functions.cpp` & `solvers_help_functions.h`: Core utility functions for assignments, flipping variables, checking satisfied clauses, and cost calculation.
* `gsat.cpp`, `gsat_rw.cpp`, `walksat.cpp`, `semi_greedy_walksat.cpp`: The algorithm implementations.

## Requirements
* A C++ compiler (e.g., GCC/g++) supporting C++11 or later.

## Compilation and Execution
To compile the project, open your terminal in the project directory and run the following command to compile all `.cpp` files together:

```bash
g++ -std=c++11 main.cpp sat_generator.cpp solvers_help_functions.cpp gsat.cpp gsat_rw.cpp walksat.cpp semi_greedy_walksat.cpp -o sat_solver
```

This will generate an executable named `sat_solver`. To run the program, type:

```bash
./sat_solver
```

## How It Works
Inside `main.cpp`, you can adjust the following parameters to test different scenarios:
* `variables_num`: Number of boolean variables.
* `clauses_num`: Number of clauses in the generated problems.
* `probability_negative`: Probability of a literal being negative.
* `problem_num`: How many different SAT problems to generate and test.
* `max_flips` & `max_tries`: Limits for the solvers to prevent infinite loops.
* `propability_rw`: Probability for a random walk in GSAT-RW and WalkSAT.
* `semi_greedy_a`: The greediness parameter 'a' for the semi-greedy initial assignment.

For each problem, the program outputs the generated clauses and then prints the best assignment found along with the remaining unsatisfied clauses (cost) for each of the 4 algorithms.

## License
MIT License

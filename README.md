# Efficient SAT Solver with Linear-Time Algorithm and Heuristic-Based Search

## Project Information
- **Description**: A SAT solver in Python that efficiently parses and solves propositional logic expressions using linear-time algorithms and heuristics.

## Project Summary
This project implements a SAT solver in Python, designed to parse and solve propositional logic expressions using logical operations like negation, conjunction, disjunction, and implication. Unlike traditional algorithms, which are exponential in nature, this solver operates in linear time, propagating truth values through the parse tree. In cases where the algorithm can't find a model, a novel approach based on guessing the truth values of unassigned atoms is used. This method involves logarithmic guesses (log2 of the number of atoms) plus a constant to improve the chances of finding a solution. The project includes visualization functions to display the parse tree and a Directed Acyclic Graph (DAG) structure for shared subformulas, optimizing the process by avoiding redundant evaluations.

## Key Features
- **Linear-Time Algorithm**: The algorithm works in linear time by propagating truth values through the parse tree, unlike traditional exponential algorithms.
- **DAG Construction**: After parsing, the common subformulas are shared in the parse tree, turning it into a Directed Acyclic Graph (DAG), optimizing the evaluation process.
- **Transformation**: Logical formulas are translated into a form that simplifies the structure while maintaining semantic equivalence.
- **Heuristic Search**: When the linear algorithm fails, it applies a heuristic approach by guessing the values of unassigned variables based on the log2 of the number of atoms plus a constant.
- **Evaluation and Visualization**: The project includes functions for evaluating logical expressions and visualizing the parse tree and DAG structure.

## How It Works
### Parsing
The `parse()` function tokenizes the input logical expression and constructs the parse tree, respecting the precedence of logical operators and simplifying double negations. The tree is built using `Node` objects representing each element of the logical expression.

### Transformation
The `transform()` function standardizes the structure of the parse tree by applying logical equivalences, primarily reducing the formula to negations and conjunctions, which are easier to evaluate.

### Truth Propagation
The `propagate_truth()` function recursively propagates truth values through the parse tree under the assumption that the formula is true. It assigns values to propositional variables while managing node identities and avoiding contradictions.

### Solving
The `solve()` function attempts to find a model that satisfies the logical formula. If the linear-time approach fails, the algorithm uses a heuristic method to make random guesses for unassigned atoms. This method improves the probability of finding a solution, especially in cases where traditional methods may fail.

## Installation
Clone the repository and install the required dependencies:
```bash
git clone https://github.com/mr-seifi/linear-sat-solver.git
cd linear-sat-solver
pip install -r requirements.txt
```
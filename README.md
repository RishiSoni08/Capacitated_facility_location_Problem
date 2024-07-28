# Capacitated Facility Location Problem (CFLP)

## Problem Definition

In this problem, we have a set of \( n = 50 \) cities and need to select among \( m = 20 \) cities that can fulfill the entire demand of the demand zones while minimizing the cost of facility constructions and the minimized distance.

## Problem Statement

We aim to:

1. Select facilities among 20 potential cities to serve the demand zones.
2. Minimize the cost of setting up facilities and the cost of transportation (minimized distance, as distance is directly proportional to cost).

## Mathematical Model

The objective is to minimize the cost of setting up the facility and the transportation cost. The mathematical formulation is as follows:

### Objective Function

\[ \text{Minimize} \quad \sum_{i} (C_i Y_i) + \sum_{i} \sum_{j} (x_{ij} \cdot D_{ij}) \]

where:
- \( C_i \) is the capacity of facility \( i \)
- \( D_{ij} \) is the distance between facility \( i \) and demand node \( j \)

### Constraints

1. Capacity constraint for each facility:
\[ \sum_{j} (x_{ij} \cdot p_j) \leq Q_i Y_i \quad \text{for every } i \]

where:
- \( p_j \) is the demand of node \( j \)
- \( Q_i \) is the capacity of facility \( i \)
- \( Y_i \) is a binary variable indicating whether facility \( i \) is selected

2. Each demand point is connected to exactly one facility:
\[ \sum_{i} x_{ij} = 1 \quad \text{for every } j \]

3. Ensure that the capacity of the facility is more than the total demand of the connected demand nodes.

### Folder Structure

- `README.md`: Contains all the information about the project.
- `data.ipynb`: Jupyter notebook that includes the location coordinates, cost of setting up the facility, capacities, and demand of the facilities and demand zones. It also combines this information into a JSON file.
- `Combined_data.json`: The combined data file.
- `Capacitated_Facility_Location.ipynb`: Jupyter notebook with the final code for solving the CFLP.

## Usage

1. **data.ipynb**: Run this notebook to generate `data.json`.
2. **Capacitated_Facility_Location.ipynb**: Run this notebook to solve the CFLP using the data from `combined_data.json`.

## Example

Here is a brief example of how to use the data and solve the CFLP:

1. Generate the data:
    - Open and run `data.ipynb`.
    - This will create a `combined_data.json` file with all the necessary information.

2. Solve the CFLP:
    - Open and run `Capacitated_Facility_Location.ipynb`.
    - This notebook will use the data from `data.json` to find the optimal locations for the facilities and the assignment of demand nodes to these facilities while minimizing the total cost.

---

This README provides an overview of the Capacitated Facility Location Problem, the mathematical formulation, and the structure of the project. Ensure that you have all the necessary dependencies installed before running the notebooks.

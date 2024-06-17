# Genetic Algorithm for TSP
The travelling salesman problem asks the following question: "Given a list of cities and the distances between each pair of cities, what is the shortest possible route that visits each city exactlyonce and returns to the origin city?
This project showcases the application of `Genetic Algorithm` to the TSP, demonstrating the algorithm's effectiveness in solving complex optimization problems. 

![2024_06_17_0wv_Kleki (1)](https://github.com/PeymanKh/genetic_algorithm_for_TSP/assets/118134658/31aa6adf-d047-4b82-86a3-9c0f1a7fc0b6)


## Table of Contents
- [1. Genetic Algorithm](#GA)
- [2. Graph Data Structure](#graph)
- [3. City Distance Table](#data)



<a name="GA"></a>
## 1. Genetic Algorithm
A Genetic Algorithm (GA) is an evolutionary optimization technique inspired by natural selection. This algorithm will evolve over multiple generations to optimize the route, minimizing the total distance traveled. Components of the algorithm are:
1. **Population Initialization**: To initialize the genetic algorithm, we generate a population of possible solutions to the TSP. Each individual in this population represents a potential route that visits each city exactly once. These individuals (or chromosomes) are generated by shuffling a list of all cities to create random tours. This randomized approach helps in covering a wide area of the solution space initially.
2. **Fitness Calculation**: Each chromosome's fitness is evaluated based on the inverse of the total travel distance. A *shorter* route results in *higher fitness*, promoting solutions that effectively reduce the travel distance between cities. This setup aligns with the objective of the TSP, which is to minimize the tour's total length.
3. **Selection Process**: Using a tournament selection method, we choose individuals from the current population to be parents of the next generation. In this approach, a subset of the population competes against each other, and the individual with the highest fitness (i.e., shortest route) is selected. This method helps maintain diversity within the population while favoring stronger candidates.
4. **Crossover Operation**: We apply an ordered crossover mechanism to mix genetic information between pairs of parent chromosomes. This process involves selecting a segment from one parent and filling in the remaining cities in order from the other parent, preserving the order of cities as they appear. Such crossovers ensure that offspring inherit good traits from both parents, which can potentially lead to better routes.
5. **Mutation Mechanism**: To introduce variability into the offspring and avoid premature convergence on local optima, we perform mutation by swapping two cities in a route. The probability of mutation is kept relatively low to prevent excessive randomization, which might otherwise disrupt the evolution of good traits in the population.
6. **Generation Update**: After creating a new generation through crossover and mutation, we recalculate the fitness for each individual. The cycle of selection, crossover, and mutation repeats over several generations, allowing the algorithm to explore and exploit the solution space effectively.
7. **Convergence**: The algorithm runs for a predefined number of generations or until a satisfactory solution is found. The best route at the end of these generations is considered as the optimal solution for the TSP given the current setup.


<a name="graph"></a>
## 2. Graph Data Structure
Quick retrieval of distance data during the execution of the genetic algorithm is crucial. That is why we implement a graph data structure from scratch to represent each city as a node and the distances between cities as weighted edges. A graph data structure is a collection of nodes (vertices) and edges connecting pairs of nodes. It is used to represent relationships or connections between entities.

<a name="data"></a>
## 3. City Distance Table
We use the data provided in the table for TSP distances. This table includes the distances between each pair of cities in kilometres, serving as the input for our genetic algorithm to determine the optimal route.
![image](https://github.com/PeymanKh/genetic_algorithm_for_TSP/assets/118134658/117ad31e-688b-4480-afff-0ccefe37d746)




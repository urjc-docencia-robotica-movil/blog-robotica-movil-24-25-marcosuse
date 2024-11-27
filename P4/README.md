# P4 - Global Navigation

## Table of Contents
1. [Practice](#practice)
2. [Algorithm Implementation](#algorithm-implementation)
3. [Problems and Testing](#problems-and-testing)
4. [Videos](#videos)

## Practice

The goal of this practice is to program a global navigation algorithm based on the **Gradient Path Planning** method for a taxi navigating a city. We click on the city map to select a target destination, and the taxi must use the implemented algorithm to find and follow the shortest route to that target. When the car is navigating and recibes another target, the new target is stored in a queue and done later. 
### Key Features
- The car only has access to its position and the global map (free and occupied spaces).
- The map is used to calculate a cost grid and determine the optimal path.
- **Wave Front Algorithm** is used to compute the cost grid by expanding a wave from the target.

## Algorithm Implementation

This practice involves the following key components:

### 1. Wave Front Algorithm
A Breadth-First Search algorithm is used to calculate the cost of moving from each cell in the map to the target:
- The wave expands from the target until reaching the car.
- Obstacles are accounted for to ensure the cost grid represents realistic paths.

### 2. Obstacle Expansion
To avoid unsafe navigation near walls, a procedure was added to increase the cost of cells near obstacles. This ensures that the car prefers paths that maintain a safe distance from walls.

### 3. Gradient Navigation
The car navigates based on the cost gradient:
- At each step, the algorithm evaluates the surrounding cells.
- The car moves in the direction where the cost decreases the most, avoiding the need for pre-planned waypoints.

## Problems and Testing

### Problems
Several challenges were encountered during implementation:
- **Obstacle Avoidance:** Ensuring the car does not collide with walls while navigating. To do that i had to gues the correct number of pixels each wall have to expand and the cost of it
- **Expansion time:** becouse of the number of pixels we had to process, the expansion last longer than i expected so i had to make the algorithim to show the resulst every X iterations, that makes the wave go so much faster and the diference is not visible.

### Tests
The algorithm was tested to verify:
1. The car efficiently calculates the cost grid of the map and it navigates efficiently.
2. It maintains a safe distance from walls and avoids collisions.
3. Correct behavior in edge cases, such as targets near walls or tight spaces.

## Videos

Below are demonstration videos showcasing the taxi’s navigation in various scenarios. The videos include examples of:
- navigation to one target

[one target]()

-navigation to multiple targets

[multiple targets]()

- near wall target

[near wall]()




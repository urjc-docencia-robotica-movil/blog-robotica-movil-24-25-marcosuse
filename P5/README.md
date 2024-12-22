# P5 - Montecarlo Laser Localization

## Table of Contents
1. [Objective](#objective)
2. [Implementation Details](#implementation-details)
   - [Particle Initialization](#particle-initialization)
   - [Weight Estimation](#weight-estimation)
   - [Optimization and Efficiency](#optimization-and-efficiency)
3. [Problems and Testing](#problems-and-testing)
4. [Videos](#videos)

## Objective

The goal of this practice is to program a localization algorithm based on the **Monte Carlo method**. The developed algorithm estimates the robot's position on a map using:
- A laser sensor
- The map.

## Implementation Details

### Particle Initialization
- **Objective:** Generate a set of particles randomly distributed across the map's free space.
- **Implementation:**
  - Particles are initialized with random x, y, and orientation values.
  - Particles can appear in every part of the map
  - The probability of each particle initialy is 0.5 becouse we dont know anything yet..

### Weight Estimation
- **Objective:** Assign probabilitys to particles by comparing theoretical and actual laser readings.
- **Implementation:**
  - For each particle, a theoretical laser scan is generated using ray tracing.
  - Differences between theoretical and actual laser readings are used to compute weights using a Gaussian model (instead of using the formula given in class):
    ```
    P = e * (-(error^2) / (2 * std_dev^2))
    ```
  - Particles on obstacles or outside the map are assigned minimal weights.

### Optimization and Efficiency
- **Techniques Used:**
  - **Parallelization:** Weight computation is parallelized using `multiprocessing` becouse this part have so much .
  - **Vectorization:** Numpy is employed for efficient numerical operations and for efficiency.

## Problems and Testing

### Problems
- **Weight Calculation:** Adjusting Gaussian parameters for realistic weight distribution.
- **Convergence:** Ensuring particles converge. And addicionally to converge in the true robot pose becouse the map has simetricals point and the map has imperfections
- **Particle restart** becouse the simetricals points sometimes the particles converge in points where the robot is not located, but with the movement of the robot the particles keep getting less probability so when the probability is low some particles restart to see if there are spaces where the probability is higher.   

### Testing
mainly all the test were focused in the correct convergence of the particles and in the efficiency of the algorithym. And also i tested edge cases where the robot is kidnapped and in the corners where the dections are worse than normal.

## Videos
I am going to show many videos.
### Number of particles

   - [750 particles]

   - [500 particles]

   - [250 particles]

   - [50 particles]

### kidnapped
   I am going to show a video where the robot change the position, becouse te model of movement, the position of the robot is going to stay still and what i move is the house

   -[kidnapped]


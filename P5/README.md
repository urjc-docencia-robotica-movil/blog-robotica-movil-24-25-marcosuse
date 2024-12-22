# P5 - Montecarlo Laser Localization

## Table of Contents
1. [Objective](#objective)
2. [Implementation Details](#implementation-details)
   - [Particle Initialization](#particle-initialization)
   - [Weight Estimation](#weight-estimation)
   - [Particle Propagation](#particle-propagation)
   - [Optimization and Efficiency](#optimization-and-efficiency)
3. [Problems and Testing](#problems-and-testing)
4. [Videos](#videos)
5. [References](#references)

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


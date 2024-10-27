## Table of Contents
1. [Practice](#practice)
2. [VFF Implementation](#vff-implementation)
3. [Challenges and Testing](#challenges-and-testing)
4. [Videos](#videos)

## Practice

The goal of this practice is to program a navigation algorithm based on the Virtual Force Field (VFF) to drive an autonomous Formula 1 car around a circuit while avoiding obstacles. The car must stay on track, guided by *waypoints* that act as targets, while avoiding collisions with the circuit's walls and other obstacles.

### Hardware

The car is equipped with a front-facing laser sensor that scans the surroundings for obstacles. This laser data is used to calculate the repulsive forces. These forces steer the car toward the next waypoint while simultaneously avoiding obstacles.

## VFF Implementation

In this project, we implement three main force vectors to determine the car’s movement and behavior:

1. **Attractive Force Vector**: This vector drives the car toward the next target waypoint. It adjusts based on the position of the car relative to the target, making sure the car stays on track.

2. **Repulsive Force Vector**: The repulsive force pushes the car away from nearby obstacles using laser sensor data. Obstacles closer to the car generate stronger repulsive forces.

3. **Resultant Force Vector**: This is the sum of the attractive and repulsive vectors. It provides the final force direction and speed settings, which we use to set the car's velocity and turn commands.

### Velocity Control

The car’s speed is controlled based on the relative strength of the resultant force vector. For example, if the car is in a narrow section or approaching a tight corner, the speed is reduced. Faster speeds are set in straight sections with fewer obstacles.

### Behavior of the car 
The behavior of the car is based in a changing role function:

- when the car has an obstacle it behaves as a normal VFF.
- when the car has no obstacle it accelerates.
- when the car is near a wall it tries to go away of the wall.
- when the target is near a wall the car becomes braver than it was so he has to be near an obstacle.

## Problems and Testing

### Problems
Some of the key Problems encountered include:
- **Repulsive Force Scaling**: Adjusting the repulsive force to make sure it effectively pushes the car away from obstacles without overpowering the attractive force.
- **Boundary Detection**: Ensuring that the car detects walls at the edges of its range and avoids getting stuck near them.
- **Speed Optimization**: Balancing speed with control to avoid collisions while still completing laps efficiently.
- **Target near walls**: Detecting waypoints that are near walls that makes the car to try to go away while trying to go near it

### Tests
The algorithm was tested to check its ability to avoid obstacles and maintain a stable path toward waypoints and making sure that no waypoint is left apart.

## Videos

Below are demonstration videos showcasing the car’s behavior in different scenarios. All videos are sped up 2x for viewing efficiency.

### Test Circuit
- [Circuit avoiding obstacles](#)  

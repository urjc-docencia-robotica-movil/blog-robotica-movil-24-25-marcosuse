# Mobile Robotics Blog 24-25 - MarcosUse

## Table of Contents
1. [Practice](#practice)
2. [Logic](#logic)
3. [Problems and Tests](#problems-and-tests)
4. [Videos](#videos)

## Practice

This project focuses on solving the problem of a "Roomba," an autonomous robot used for cleaning a house. In this case, the Roomba cannot access its position on the map, which complicates its efficient operation. To address this limitation, randomness is used to allow the robot to effectively navigate the house.

### Hardware

In this project, we are using two main types of sensors:

#### Bumper

One of the sensors is the "bumper," which, after receiving a command, returns a value of 0 if there is no collision and 1 if a collision has occurred. Additionally, it has three bumpers on each side, which return values of 0, 1, or 2 depending on which bumper has been triggered.

#### Laser

Another key sensor is the laser. This sensor has a 180-degree field of view from the side of the robot and works by emitting pulsed laser light into the environment. These pulses travel at the speed of light, bounce off surrounding objects, and return to the sensor. By measuring the time they take to return, the sensor calculates the distance to the objects.

## Logic

The program's logic follows the following state diagram:

![State Diagram](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/Diagrama_vacumm.drawio(1).png)

At first glance, it may seem complicated, but it will become clearer upon explanation.

### Modules

#### Forward
The "Forward" module is responsible for moving straight ahead and if it takes too much time it rotates while is going forward. This module can transition to the states: `Disturn`, `Back`, or `Spiral`.

#### Back
This module makes the robot move backward for a random amount of time, and it can transition to the states: `Turn`, `Starturn`, or `Disturn`.

#### Turn
The "Turn" module makes the robot turn in a random direction for a specified amount of time. It always transitions to `Forward`.

#### Disturn
The "Disturn" module makes the robot turn towards a direction where there is more than 2 meters of space ahead. It always transitions to `Forward`.

#### Starturn
The "Starturn" module performs slight turns so that the robot moves in a star pattern. It always transitions to `Forward`.

#### Spiral
The "Spiral" module makes the robot follow a spiral pattern, adjusting its speed over time. It always transitions to `Back`.

## Problems and Tests

### Problems

One of the main challenges I faced during this practice was deciding how to approach the code design. I opted for a solution in which many decisions, such as the turning angle and the duration of the backward movement, are made randomly. While this is not the most efficient approach, the code sometimes works well, though other times it does not.

Another issue I encountered, which seems to be exclusive to me (as my classmates did not experience it), is that the laser sensor appears to collapse when the robot is too close to an object, returning incorrect values. I am unsure how this will behave on other computers.

One problem related to the program itself is that when the robot enters a room, it sometimes gets stuck. To address this, I implemented the `Disturn` state, which makes the robot turn towards a direction with enough space to move forward.

Finally the last problem i saw and i completely dislike is that the chairs in the corner can be passed from below so the map is wrong and scaping from there is so difficult.


### Tests

The tests I have conducted primarily focus on ensuring the robot can escape tight spaces. Although it still struggles, it usually manages to get out within 3 minutes and 30 seconds, which I consider a decent outcome.

I also conducted tests with the laser sensor to understand why it wasn't working properly. After numerous tests in different environments, I still haven't identified the cause of the incorrect readings.

# Videos
Below are videos and screenshots showing when the code performed correctly and when it did not.
## Screenshots
the following screenshots were made when the robot was running 10 minutes straight

![cap 1](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/Captura%20desde%202024-09-29%2017-08-09.png)

![cap 2](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/Captura%20desde%202024-09-28%2020-03-48.png)

## videos
the following video is a simulation in 15 minutes of the robot

![video](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/output.gif)

this las 17 min but is better approach

![video 2](https://github.com/urjc-docencia-robotica-movil/blog-robotica-movil-24-25-marcosuse/blob/main/r_movil/vacumg.gif)

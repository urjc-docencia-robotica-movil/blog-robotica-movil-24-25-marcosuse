# Mobile Robotics Blog 24-25 - MarcosUse

## Table of Contents
1. [Practice](#practice)
2. [PID](#PID)
3. [Problems and Tests](#problems-and-tests)
4. [Videos](#videos)

## Practice

This project focuses on driving an autonomous F1 car. First of all, the circuit we are racing has a red line in the centre and the F1 car have to stay almost all the time above it, but the car also have to be fast enough to travel arround the circuit in the less time posible, so we have to implement some tools to decelerate in the curves an accelerate in the rects.

### Hardware

In this project, we are using only one sensors:
### Camera
We are using one camera in the front of the car, it is meant to be used for following the line, but there are many problems with the normal camera so we have to aply a mask for only seeing the red part. the mask i am using HSV to make the mask becouse it is way more effective than using the BGR becouse with the HSV we ca exclude a filter of the white that has all the colors.

## PID


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

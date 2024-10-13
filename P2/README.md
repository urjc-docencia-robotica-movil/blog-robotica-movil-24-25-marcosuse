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
the PID is a way of getting rid of an error and in this case we are using it for two diferents problems, the turn in a curve and the accelerationd and deceleration. Every PID has three attributes and they are P, I and D. The P is the proportional part so it means that only with this part the F1 is going to be oscilating all the time and we calculate it by multiplicating the error with a kp chosen by me. The I part is the integral part and his job is to get rid of the estacionary error and we calculate it by adding all the errors acumulated. And the las part, the D part is the derivative part and the funcionality of this part is to make the turn smoother so we dont have to be going up and down of the red line.
### Curve 
As i am using the pid for the curves by calculating the centre of the image and the average of the red parts in the center row of the image and with that we substract the center of the image with the average of the red parts in the center row and that is how i calculate my error.
### acceleration and deceleration 
With the output i get from the pid of the curve i calculate the error of the aceleration, with mi PID i have to compare the error with 0 so i substract 1 with the output of the curve pid, and with that if the error is lower than 1 i accelerate and if the error is greater the F1 decelerate. 

## Problems and Tests

### Problems
There were many problem with this practic, one of them was the mask of the camera, i was doing it with rgb and the color white was always red and that gives us so many problems so i resolve it by changing rgb with HSV, other problem was that the camera was not exactly in the center so i had to move it, another problem was that  


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

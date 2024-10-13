# Mobile Robotics Blog 24-25 - MarcosUse

## Table of Contents
1. [Practice](#practice)
2. [PID](#pid)
3. [Problems and Tests](#problems-and-tests)
4. [Videos](#videos)

## Practice

This project focuses on driving an autonomous F1 car. First of all, the circuit we are racing on has a red line in the center, and the F1 car has to stay almost all the time above it. However, the car also needs to be fast enough to travel around the circuit in the shortest time possible. Therefore, we have to implement some tools to decelerate in the curves and accelerate on the straights.

### Hardware

In this project, we are using only one sensor:

### Camera
We are using one camera at the front of the car, which is used for following the line. However, there are many problems with the regular camera, so we need to apply a mask to detect only the red part. I am using HSV to create the mask because it is much more effective than using BGR. With HSV, we can exclude a filter for the white color, which contains all colors.

## PID
The PID is a method of reducing error, and in this case, we are using it for two different problems: turning in curves and managing acceleration and deceleration. Every PID has three components: P, I, and D. The P is the proportional part, which means that, using only this part, the F1 car will oscillate all the time. We calculate it by multiplying the error by a Kp value that I chose. The I part is the integral component, which helps to eliminate the steady-state error by summing all accumulated errors. Lastly, the D part is the derivative component, which helps smooth the turns so that we don’t constantly go up and down over the red line.

### Curve
I use the PID for the curves by calculating the center of the image and the average of the red parts in the center row of the image. Then, I subtract the center of the image from the average of the red parts in the center row to calculate the error.

### Acceleration and Deceleration
Using the output from the PID for the curve, I calculate the error for acceleration. I compare the error with 0 by subtracting 1 from the output of the curve PID. If the error is less than 1, I accelerate; if the error is greater, the F1 car decelerates.

## Problems and Tests

### Problems
There were many problems with this project. One of them was the camera mask. Initially, I was using RGB, and the white color was always detected as red, which caused many issues. I solved it by switching from RGB to HSV. Another issue was that the camera wasn’t exactly centered, so I had to adjust its position. Additionally, my computer didn’t have enough processing power to run the program efficiently, which limited the performance of my code. Another problem was that if the camera lost track of the line, the car needed to return to it. I implemented a simple code to fix this issue. Another issue I encountered was that after I thought I had perfectly tuned the PID, I would restart the program, and the PID would break again, so I had to fix it each time. Adjusting the PID is very time-consuming. The last problem was that during the Ackermann test, I tuned the PID perfectly, but in the same spot every time, the car flipped over as if it hit an invisible wall.

### Tests
This time, I was always testing my program on the simple circuit, using the normal configuration and Ackermann steering. This is because, for some reason, when I change the circuit, the program's Hz drastically decreases. Another thing that took most of my time was adjusting the PID values.

## Videos
Below are videos of the simple circuit without ackerman and with ackerman, and in the montmelo circuit without ackerman. All the videos are in 2X.

### simple circuit
In This part i get 30 secs aprox.

[Simple](https://urjc-my.sharepoint.com/:v:/g/personal/m_useros_2022_alumnos_urjc_es/EQTt9frgUwpNkVt4oVnQaq8BSJr93ms-8NMZaChUQ3B0eg?e=J5tyyc&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)


### montmelo circuit
In This part i get 360 secs aprox.

[Montmelo](https://urjc-my.sharepoint.com/:v:/g/personal/m_useros_2022_alumnos_urjc_es/ETTBkP2hLAZPhygpfE21x3wBvwxVX-hhKquLwmcACaxNgw?e=p20HwW&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)


### Ackerman simple circuit.
In This part i get 80 secs aprox until it stops.

[Video Ackerman crashed](https://urjc-my.sharepoint.com/:v:/g/personal/m_useros_2022_alumnos_urjc_es/EYafU0l0vvhCtcBd-NyHfYMBjRgDGWDA2XxHD_7vG95lCg?e=Ol6VkM&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)



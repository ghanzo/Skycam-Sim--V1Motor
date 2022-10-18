![nfl-camera](https://user-images.githubusercontent.com/22437742/196407908-cf30e197-1789-40a8-95c8-85206209ca5d.jpg)
# Skycam-Sim - Version 1

## Demonstrates stepper motor control to perform SkyCam movement in 2D

### SkyCam used in NFL for dynamic aerial footage


The camera can be positioned anywhere over the field by extending the 4 cables to the correct lengths!

Controlled by 4 motors placed at ground level outside stadium.
Cables strung in a rectangular pattern over the top of the stadium.
Cables meet in the center of the stadium and connect to the camera.
Cables length is controlled by motors.
All 4 lengths determine the position.

## Movement
Movement of the camera requires non-linear motor behavior
Stepper motors STEP a fraction of an rpm per electronic pulse
RPM can be controlled by rate of pulses sent to motors

### Determine the step timing

Start by creating a funtion that translates a point to another within the grid
The point should move evenly across time

### We start by determining the dimensions of the grid

![image](https://user-images.githubusercontent.com/22437742/196411690-18810a2d-2860-47a4-bd04-6d09efc81c22.png)

### We then declare the variables of the translation

![image](https://user-images.githubusercontent.com/22437742/196411988-76732b6d-7b40-4e05-bcfc-9a6930f4b04a.png)

### We then declare a time-to and a time-total

![image](https://user-images.githubusercontent.com/22437742/196412625-fafc8d33-6a49-435f-b22b-c55925f699d4.png)

## Lastly the x and y of the translations position across the time interval can be determined with these formulas

![image](https://user-images.githubusercontent.com/22437742/196412707-f9860628-331d-4ae5-967b-d64d702c3059.png)


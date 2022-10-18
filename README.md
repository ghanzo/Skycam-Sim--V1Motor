![nfl-camera](https://user-images.githubusercontent.com/22437742/196407908-cf30e197-1789-40a8-95c8-85206209ca5d.jpg)
# Skycam-Sim - Version 1

## Motor Control for SkyCam movement in 2D

### NFL Skycam for dynamic aerial footage


The camera can be positioned anywhere over the field by extending the 4 cables to the correct lengths!

Controlled by 4 motors placed at ground level outside stadium.
Cables strung in a rectangular pattern over the top of the stadium.
Cables meet in the center of the stadium and connect to the camera.
Cables length is controlled by motors.
All 4 lengths determine the position.

# Movement
Movement of the camera requires non-linear motor behavior
Stepper motors STEP a fraction of an rpm per electronic pulse
RPM can be controlled by rate of pulses sent to motors

## Defining Variables

### We start by determining the dimensions of the grid

![image](https://user-images.githubusercontent.com/22437742/196411690-18810a2d-2860-47a4-bd04-6d09efc81c22.png)

### We then declare the variables of the translation

![image](https://user-images.githubusercontent.com/22437742/196411988-76732b6d-7b40-4e05-bcfc-9a6930f4b04a.png)

### We then declare a time-to and a time-total

![image](https://user-images.githubusercontent.com/22437742/196412625-fafc8d33-6a49-435f-b22b-c55925f699d4.png)

## (X,Y) Camera Position across translation found with these formulas

![image](https://user-images.githubusercontent.com/22437742/196412707-f9860628-331d-4ae5-967b-d64d702c3059.png)

## Cable Length from Top-Right-Motor found with this formula 

![image](https://user-images.githubusercontent.com/22437742/196414562-5f51b5f6-e9d3-4876-b39b-f2f97f648c0a.png)


# Steppig the motor

Once we know what the length of the cable *should* be at any time, we then step to that position, and make a variable that steps once more. If the next step is closer to the requisite position, then we step once more, and calculate the next one after again. So the resolution of the cable length is off by 1/2 step distance, but since there are hundreds of steps per rpm that is close enough. If the steps were much larger we would see shaky movement, but since they are small the movement will be smooth.

# This instantiation

This just demonstrates one translation and one motor using python package turtle for graphically representing the translation. You can see that the shuttle moves at a constant rate but the top right corner step rate changes non linearly throughout the translation.

## Code can be run at my repl

https://replit.com/@gonzo/movement-via-time#main.py

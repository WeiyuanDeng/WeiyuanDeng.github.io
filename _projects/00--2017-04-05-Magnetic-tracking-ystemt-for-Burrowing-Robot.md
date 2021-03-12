---
layout: project
title: Magnetic Localization System for Burrowing Robot in 1-D and 2-D
date: September 22, 2017
image: /public/images/2dgraph.jpg
---

## Overview
The objective of the project is to design a magnetic tracking system that can work under granular material for a burrowing robot. In this study, a single dipole magnet will be attached to the robot with 6-degrees of freedom. To detect the 6-degrees of freedom robot, at least 6 independent measurements of the magnetic field will be needed. Therefore, a two sensor geometry and a single dipole magnet will be used in the study. Arduino is used for communication between PC and sensors. Program language
used in the study is Python.

### Sensor
The magnetometers used in the project are [MLX90393](https://www.sparkfun.com/products/14294) from [Sparkfun](https://www.sparkfun.com/).

![sensor_new](/public/images/sensor_new.jpg)

 It is a tri-axial magnetic sensor capable of sensing very small fields (like the Earth’s magnetic field) while behaving as one would want expect during saturation in larger fields (like a nearby magnet).It has a resolution of 0.161µT, and a max full scale resolution of 44,000µT. The sensor supports both I2C and SPI communication protocols, and has a user selectable I2C address that supports upto four sensors on the I2C bus at a time.

The farthest distance that the MLX90393 can sense the magnetic field of the magnet used in the study is around 350 mm from the breakout board.

Here is the [datasheet for MLX90393](https://cdn.sparkfun.com/assets/learn_tutorials/5/7/7/MLX90393-Datasheet-Melexis.PDF).

### Microcontroller
To connect the sensor with the computer, an [Arduino Uno R3](https://www.arduino.cc/en/Main/ArduinoBoardUno) is used.

![arduino](/public/images/arduinouno.jpg)

To get started with Arduino Uno, [here](https://www.arduino.cc/en/Guide/HomePage) is a guide from Arduino official website.

To communicate with the sensor with Arduino, Ted Yapo has written a good Arduino Library for the MLX90393, which could be found [here](https://github.com/tedyapo/arduino-MLX90393).

### Qwiic Cable
All Qwiic cables have the following color scheme and arrangement:
Black = GND
Red = 3.3V
Blue = SDA
Yellow = SCL

![Pinout](/public/images/pinout.png)

### Magnet
The dipole magnet used in the study is a cylinder with its North pole was marked with a black dot. The magnetic strength at a distance d from the magnet (dipole points to z-axis direction):
Bz =b/(d^3), where b is a constant.

It has been verified that the dipole is tilted by doing a real time plot while rotating the magnet about the z-axis direction by hand. To prove it, the magnet was placed at a distance of 50mm, readings of magnetic strength in all three directions were recorded and plotted when the magnet rotated about its zaxis by 0°, 45°, 90°, 135°, 180°, 225°, 270°, 315°, 360°. After fitting the curve, they show a pattern of Sine and Cosine waves, which indicates that the magnet is tilted with a specific angle.

![tilt](/public/images/tilt.jpg)

### 1-D Procdure

Tape engineering paper on a wooden table. The sensor is taped on the engineering paper and assume the position of the center of the chip on the sensor is the origin. Magnet can be placed on anywhere on the engineering paper with its dipole points towards the z-direction, as the figure shows below. As the magnet is tilted, make sure that it is always tilted to the direction of the sensor during the calibration and test.

![1-D](/public/images/1-D.jpg)

To do calibration, take readings of the magnetic strength in the z-axis direction with the magnet placed 200 mm, 120 mm, 80 mm, 50 mm and 30 mm from the sensor.

![1-Dposition](/public/images/1-Dposition.jpg)

With least square method, the parameters b, C, and d0 that fit the model best could be found. Then place the magnet anywhere on the engineering paper within the range of 250mm, record its real time magnetic strength in z-axis direction. With the least square method, find the best fit distance from the sensor.

In the test, measurements were taken every 30 seconds. 6 measurements were taken. The distances from the sensor are 43mm, 60mm, 94mm, 140mm, 181mm, 223mm

### 1-D Results
After running the code 1-D.py, the program found values of b, d0, C that fit the 1-D model the best: b =19488302.3327, C = -5.97429830037, d0 = -1.10433116782.

![1-Dvalue](/public/images/1-Dvalue.jpg)

By doing test at distances of 43mm, 60mm, 94mm, 140mm, 181mm, 223mm from the chip of the sensor, the predicted distance values were given by the program. The error was calculated by subtracting actual distance from predicted distance.

![cal1d](/public/images/cal1d.png)

To better understand the results, below is a plot of the error as a function of actual distance. It could be seen that in a range of around 40mm to 150mm, the error is in a reasonable range, about 2.5% to 3.5%. When the distance is larger than 150mm or smaller than 40mm, error grows.

![error1d](/public/images/error1d.png)

### 2-D Procdure

Tape engineering paper on a wooden table. The sensors are taped on the engineering paper and they are 75mm away from each other. Assume the position of the center of the chip on the sensor 2 is the origin. Magnet can be placed on anywhere on the engineering paper with its dipole points towards the z-direction, as the figure shows below. As the magnet is tilted, make sure that it is always tilted to the direction of the sensor during the calibration and test.

![2-D](/public/images/2-D.jpg)

To communicate with different sensor, user would send command to the port with terminal. “1” stands for sensor 1, “2” stands for sensor 2. Then Arduino read the command from the port and call mlx.changeaddr() and set the pin of A1 to 0 or 1 to switch sensors.

To do calibration, take readings of the magnetic strength in the z-axis direction from both sensors with the magnet placed at (-25, 0), (-40, 15), (-50, 25), (-50, 50), (-25, 75), (-100, 75), (75, 100), (-50, 125), (75, 250), (15, 20), (30, 0).

![2-Dposition](/public/images/2-Dposition.png)

With least square method, the parameters b1, b2, x10, y10, x20, y20, C1 and C2 that fit the model best could be found.

Then place the magnet anywhere on the engineering paper within the range of engineering paper, record its real time magnetic strength in z-axis direction from two sensors. With the least square method, plug in b1, b2, C1 and C2 find the best fit distances from each sensor. Then use the distance from the two sensors with least square method, plug in x10, y10, x20, y20, the
position of the magnet could be found.

In the test, measurements were taken every 90 seconds. 6 measurements from each sensor were taken. Points for testing are (25, 25), (50, 150), (-50, 175), (-15, 60), (-55, 105) and (-55, 5).

### 2-D Results
After running the code 2-D.py, the program found values of b, d0, C that fit the 2-D model the best: b1 =18336066.3418, C1 = -79.4384354297, x10 = -2.78449875435, y10 = -4.1282395466; b2 =24767501.5711, C2 = -57.8547336877, x20 = -1.53861147238, y20 = -0.50534924789.

![2-Dvalue](/public/images/2-Dvalue.jpg)

By doing test at points (25, 25), (50, 150), (-50, 175), (-15, 60), (-55, 105), (-55, 5), the predicted positions were given by the program. Error was calculated according to formula 𝐸 = (𝑥_𝑝𝑟𝑒𝑑𝑖𝑐𝑡𝑒𝑑 − 𝑥_𝑎𝑐𝑡𝑢𝑎𝑙)^2 + (𝑦_𝑝𝑟𝑒𝑑𝑖𝑐𝑡𝑒𝑑 − 𝑦_𝑎𝑐𝑡𝑢𝑎𝑙)^2
.

![cal2d](/public/images/cal2d.png)

To better understand the results, below is a plot of the actual positions and the corresponding predicted positions of the magnet. It could be seen that when the magnet was relatively far from the sensor, the error grows larger.

![error2d](/public/images/error2d.png)

### Conclusion
The prediction of distance and accuracy of the 1-D model is reasonable in a range of distance around 40mm to 150mm. When the magnet is too close to the sensor, error becomes larger. As the magnet getting closer to the magnet, the magnetic strength that the sensor senses becomes very strong, a little distance error could cause a huge different to the magnetic strength. Therefore, the error at a distance less than 40mm may be caused by moving and placing the magnet by hand which leading to an inaccurate actual distance value.

The prediction of position and accuracy of the 2-D model is reasonable in an area that near the two sensor, but it becomes worse if the magnet was getting further. When the magnet is getting further from the sensor, error grows. That may be caused by the resolution of the sensor and other fields in the environment. When the magnet is very far from the sensor, the fields in the environment has more effect on the measured magnetic strength while the difference of magnetic strength caused by distance would be smaller and less significant. Therefore, it is necessary to place the magnet in a reasonable range or replace the magnet in the study with a stronger one.

Although in the calibration and test process, the magnet was placed to be always tilted to the direction of the sensor, it could still has error as it was all doing by hand.  Tiny difference of the angle around z-axis between each measurement would leading to significant difference of the magnetic strength values.

As the magnet is tiled, and two sensors were used in the 2-D model study, it was impossible to make it tilted to a particular direction that has no effect on both sensors. The tilt of the magnet would always influence the reading of the magnetic strength. To solve it, offset that can correct angles of pitch and yaw could be introduced in the 2-D model, which is studying in 3-D model.

To improve it, devices with better accuracy could be used to fix and move the magnet, thus a more accurate measurements of the distance between magnet and sensor could be obtained.

(Code could be found [here](https://github.com/WeiyuanDeng/MagneticTrackingSystem))
(3-D model is in design and testing...)

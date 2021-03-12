---
layout: project
title: Pitching Machine Optimization
date: January 12, 2016
image: /public/images/pitchingmachine.png
---

Group Members: Jordon Roseman, Peiming Zhu, Yeajun Yoo, Lifu Wang, Mark Mallory

## Overview
Design a high capacity ball feeder that can fit different types of pitching machines and create a prototype. So we designed a high capacity ball feeder with a hopper that sits on the ground and delivers the balls one at a time into the pitching machine.

### Engineering Requirement and QFD
1. Ball Lift rpm: 15
2. Hopper size: 5 cubic ft.
3. Diameter of Ball Path: 4”
4. Motor Power: 0.2 hp
5  Wheels on the bottom
6. Visible Delivery Tube
7. Proper Gear Ratios
8. Separator rpm: 12.5
9. Lift Height: 5’
10. Lift Blade Angle: 14”

Using a list of the most important engineering requirements, it was possible to cross reference the physical aspects of the design with the customer requirements.  This allowed the team to see exactly which requirement each piece of the design was satisfying.  Scoring each requirement accordingly, it provided the team with a numerical value of importance for each aspect of the design.  This process is done by using a QFD.

![QFD](/public/images/QFD.png)

### Product Design
Assemble of the Frame: The main function structure includes the ball bin, the elevator auger, the separator disc and the transmission system.

![frame1](/public/images/frame1.png)

![frame2](/public/images/frame2.png)

![frame3](/public/images/frame3.png)

Sketch of the ball pin: For our container, the designed height is 16 inches and the designed width and height is about 2 feet. For the disc, the designed diameter is 12 inches. The total volume of the designed bin is about 7000 in3.

![ballpin](/public/images/ballpin.png)

Sketch of the bottom disc: The function of the bottom disc is mostly for preventing the ball from being jamming. It’s driven by the motor, sharing power with the helical auger.

![bottomdisc](/public/images/bottomdisc.png)

Sketch of deliver tube:

![delivertube](/public/images/delivertube.png)

Sketch of disc housing:

![dischousing](/public/images/dischousing.png)

Sketch of ball elevator: The elevator is also driven by the motor through the transmitting system. It’s designed to have about 5 inches to fit our design requirement.

![elevator](/public/images/elevator.png)

### Design Evaluation
For the ball feeder, what we cares most is the power that drive the separator and the lifts, together with the torque. The calculation was used for the product evaluation, by figuring out the total energy cost and the total torque needed.

The total torque that ball seperator needed:

![ballformula1](/public/images/ballformula1.png)

As our designed value, T = 102.8 lb in.

The total torque that elevator needed:

![ballformula2](/public/images/ballformula2.png)

As our designed value, T = 38.35 lb in.

Below is a figure shows the torque needed for the ball separator and ball elevator.

![torque](/public/images/torque.png)

Take the safety factor of 5, the final result of the total power cost is no more than 0.2 hp.

Use ANSYS for the stress safety analysis.

ANSYS structure analysis for ball elevator safety:

![ansys1](/public/images/ansys1.png)

ANSYS structure analysis for separator disc safety:

![ansys2](/public/images/ansys2.png)

For more reliability, the actual model must be made and tested.

### Impact Statement
In the design of the high capacity ball feeder, potential impact to the environment was taken in consideration in only one design aspect, the energy consumption. The power consumption of the motor was optimized in order guarantee the energy efficiency ratio remained low. As a society, the use of the high capacity ball feeder will allow for more efficient batting practices by minimizing the amount of time to refill the pitching machine with balls. This may lead to an increase in the baseball player’s skill at batting, furthermore leading to higher attendance at the sporting event. In the design of the high capacity ball feeder, safety was taken in consideration in regards with protecting the user from the moving mechanical parts. In regards with entrepreneurial potential, the design provided up to a 100 ball capacity, which is unique to the market. The potential customer include but not limited to: professional baseball team, college athletic programs, high school athletic programs, batting cages, and general public consumer.

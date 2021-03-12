---
layout: project
title: Plastic-Recycling Crusher Design
date: August 24, 2015
image: /public/images/crusher.jpg
---

Group Members: Zongying Xu, Lifu Wang, Yufeng Zhang

## Overview
Designed a plastic crusher for office according to Creo and gave loading analysis to varies structures with ANSYS

### Premilinary Conceptual Design
Manual Powered: decrease cost, easier for assemly, safe for using, lighter.

Blocks:
1. Basically cubic
2. Size of 13 in * 11.5 in * (15+3.5) in length*width*(body height + cover height)
3. Top block: avoid contact between cutters and human
4. Side block: avoid plastic pieces splash out and damage gears
5. Net: allows small pieces pass thought and block big pieces
6. Thickness of block: 0.75 inches for front and back block, 0.5 inches for left and right

Connection: by screws

![crushermodel](/public/images/crushermodel.png)

### Valiadation

#### Main Shaft:

![mainshaft1](/public/images/mainshaft1.png)

![mainshaft](/public/images/mainshaft.png)

#### Handle shaft:

![handleshaft](/public/images/handleshaft.png)

![handleshaft2](/public/images/handleshaft2.png)

#### Left Block:

![leftblock](/public/images/leftblock.png)

#### Right Block:

![rightblock](/public/images/rightblock.png)

#### Bearing:

For the main shaft:
1. width: 0.5 inches (fit the block)
2. Material of 52100 Steel
3. Working temperature: -20o – 240o F
4. Connecting: press fit and fix in the block

For the handle shaft:
1. Inner diameter: 0.75 inches (fit the shaft)
2. Width: <0.5 inches (fit the block)
3. Material: 52100 Steel
4. Working temperature: -20o – 240o F
5. Connecting: press fit, fix in the block

#### Front Cover:

![frontcover](/public/images/frontcover.png)

#### Back Cover:

![backcover](/public/images/backcover.png)

#### Gears and Handle

Gear box 1.5-3.5 gear pair (3.5)+1*(1.5): increase the force, reduce the speed; efficiency is larger when the size of two gears are not too large.
1. Material: steel
2. Connecting: press fit

Handle: decrease the input force; freely control
1. Material: steel
2. Connecting: thread in

![gearhandle](/public/images/gearhandle.png)

#### Cutter

![cutter](/public/images/cutter.png)

Outer ring design: 60o to reduce the pressure on the blade; 0.58 in. thick, 1 ft. for total 20 element ( cutter-block-cutter… ); outer diameter 1.75 inches; enough fillet for reducing the stress concentration

Inner ring design: hexagon shape for connection; side length: 0.72 (shaft diameter 1.25); press fit

Cutter ANSYS analysis. Design regulation:
1. Stress is concentrated around the screw hole
2. Change the design into Hexagon press fit connection

![cutteransys](/public/images/cutteransys.png)

#### Cutter Block

![cutterblock](/public/images/cutterblock.png)

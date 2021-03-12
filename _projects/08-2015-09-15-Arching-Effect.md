---
layout: project
title: Analysis of Force Transfer and Arching Effect with PFC3D
date: September 15, 2015
image: /public/images/arching.jpg
---

## Overview

Arching effect is a universal phenomenon that occurs when the stress is transferred from the yielding part of the soil to the adjacent rigid zone is known arching effect of soil.

The stuy aimed at making a comparison analysis of the arching effect and force transmission in a sand pile and in as silo stored with sand, by means of DEM (discrete element method)

![silo](/public/images/silo.png)

### Modeling and Simulation
Both the sand pile and silo contain sphere and non-sphere granule. Ignore viscosity and humidity. Assume friction coefficient is 0.5.

In the model presented by the study, non-sphere granule was constructed by randomly connect two sphere. It can also be done by connect three or four sphere together.

With the PFC3D software, construct the model of sand pile and and silo stored with sand.

#### Sand Pile

1. Construct a rigid plane, it is called a wall.

![wall](/public/images/wall.png)

2. Construct a cyclinder wall.

![silowall](/public/images/silowall.png)

3. Randomly fill the cyclindrical container with large amount of sphere and non-sphere.

![siloball](/public/images/siloball.png)

4. Delete the bottom of the container to release granule only under gravity, then obtain a sand pile.

![sandpile](/public/images/sandpile.png)

5. Set the color of contact force shown as black, obtain a sand pile with clear force chain distribution.

![sandforce1](/public/images/sandforce1.png)

![sandforce2](/public/images/sandforce2.png)

#### Silo filled with Sand

1. Construct a rigid plane, and a cylindrical wall, set its friction coefficient to be 0.5.

![silomodel](/public/images/silomodel.png)

2. Randomly fill the silo with large amount of sphere and non-sphere.

![silofill](/public/images/silofill.png)

3. Set the color of contact force shown as black, obtain a silo filled with granule with clear force chain distribution.

![siloforce1](/public/images/sandforce1.png)

### Result Analysis

### Future Development
Modeling variety of granule (three or four spheres per granule).

Analysis of the contact force between the granule and the wall of the silo.

Add more granule to get more precise result.

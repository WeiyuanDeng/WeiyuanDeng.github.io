---
layout: project
title: Lithum Ion Battery Optimization
date: August 25, 2015
image: /public/images/lib.png
---

## Overview
Used Finite Element Analysis to find power density of designed LIB, analyzed the data and find the heterogeneous grain structure of LIB and finally used Matlab to recreate the grain structure and plot the correlation function

### Grain Reconstruction in 2D
A random two-phase microstructure medium can be regarded as a probability space that can be characterized with statistical approaches. Many descriptors have been proposed for quantification of heterogeneous microstructure. One of the basic tool for characterization of a heterogeneous micro-structure is the n-point correlation functions. And in the case of our study, we are using the two-point-correlation function, which is also the most widely used on among all the n-point-correlation functions.The two-point correlation function is function about the probability of two existing interested points within particular distance.

In order to make further analysis more approachable, it is important to transfer the image into binary.We crop the image to get rid of the outer boundaries which are useless for the study and characterization. In this example, we chose the image with more regular boundaries which could be more easily reconstructed. When the image is ready for characterization, the 2 point correlation functions could be applied.

The reconstruction process combine a random core selection process and a random grain filled process. In the process of core selection, the core are randomly distributed in the whole image with two criterion: the critical criterion and the grain potential energy criterion. The critical criterion is that there exists an minimum distance between two different cores, while the grain potential energy criterion is that based on the grain potential function, the new grain core are more likely to developed near the existing grain. The process of grain grow simulates the real process of a growing grain by using the random function. With typically probability of grows, for each generation, each pixel’s generation follows the same probability.

### Grain Reconstruction in 3D
Similar as 2D reconstruction, 3D reconstruction aims to simulate a more realistic model of the heterogeneous material of Lithium-Ion-Battery, for a further research. To characterize a 3D model, there are two ways: 3D rough view and 2D sectional view. For both methods, the two-point correlation function still works. Compared to the 3D rough view, the 2D sectional view is better in showing the inner structure of a heterogeneous grain.

Similar as 2D construction, the construction processes are the same in 3D construction.

The geometrical analysis of the reconstruction grains is similar to 2D: the shape of function and the two-point correlation function. However, the two-point correlation function is time costing, which will cost a huge in further researches. So the simplified two-point correlation function is useful here.
The simplified two-point correlation function model bases on the original two-point correlation function, which has been talked in the previous chapter. There are two more variables imported to control the size and accuracy.
The size factor controls the sampling size (using grid distribution), the value is between 1 and the maximum length. The accuracy factor control the minimum searching steps, the value is between 0 and 1. When the size factor equals to 1 and the accuracy factor equals to 0, the simplified two-point correlation function is exactly the same as the original one.

### Three-Dimensional Model and Simulation of LIBs Based on 3D microstructure of electrodes


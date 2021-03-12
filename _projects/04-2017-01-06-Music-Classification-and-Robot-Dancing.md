---
layout: project
title: Music Classification and Robot Dancing
date: January 06, 2017
image: /public/images/pose3.png
---

## Overview
This is a simple algorithm that is able to let a 3D humanoid robot model dance with whatever songs that is detected in the dataset while the user plays a piece of song to the microphone.

Currently supports ten songs (more could be added) with only two movement, there will be improvement on different and more movements soon.

The project can be divided into two parts. The first part is song learning and classification, the second part is the dance movement capture

### Dataset and classfication
The song learning and classification part in the dancing robot project was an implementation of Will Drevo's remarkable work, Dejavu.

The learning and classification of songs are based on audio fingerprinting. For more information about how Devaju works, please see Drevo's page for [Dejavu](https://github.com/worldveil/dejavu).

### Humanoid Robot URDF
The description of the humanoid robot is written in humanoid.urdf. It has totally 22 degrees of freedom.

This is how the humanoid robot URDF viewed (front view and side view) in Rviz, a 3D visualizer for displaying sensor data and state information from ROS.

![urdf1](/public/images/urdf1.png)

### Dancing Movements
There are 2 ways to get waving movements for the dancing part. One is given joint angle as a function of time, the other is to transform data from Kinect Skeleton Tracking to joint state information.

### Hard coded movements
For test of the movement, there are two waving poses that is only for 2-D plane. The joint state information varies with time is directly given in [waving.py](not yet uploaded).

The graph below is the front view and side view of waving pose 1, with the joint "upper_body_to_right_shoulder" fixed while the joint "right_upper_arm_to_right_elbow" moves.

![movement1](/public/images/movement1.png)

The graph below is the front view and side view of waving pose 2, with the joint "right_upper_arm_to_right_elbow" fixed while the joint "upper_body_to_right_shoulder" moves.

![movement2](/public/images/movement2.png)

### Movement Capture with Kinect Skeleton Tracking
To implement, please download [OpenNI](http://openni.ru/openni-sdk/openni-sdk-history-2/index.html) and install [openni_tracker](http://wiki.ros.org/openni_tracker).

With the skeleton tracker, the x, y and z position of the frame of each joint can be collected into a csv file and view in excel. To convert this data into joint states, movement.py was written (not yet uploaded), and it is based on the formula below.

![formula](/public/images/formula.png)

### Dance
Finally for the dancing part, each song corresponds to different movements, which was written in dancing.py (some of the lines are still left commented as there will still be improvement in movements in 2 weeks).

The project is still in developement...

---
layout: post
title: Switching from ROS to ROS2
feature-img: "img/sample_feature_img_2.png"
---

Since its advent in 2007, ROS has sought to made the lives of people working in the field of Robotics much easier. The custom message passing system, the discovery, and the serialization of messages really helped in implementing the communication protocol that is in place today. This is understandable in retrospect when we take a look at why ROS needed to exist in the first place. ROS was originally developed to be the middleware for the PR2 robot, which was built by Willow Garage. So, it was mostly written keeping one single(custom) robot architechture in mind. As more and more people started using ROS for a variety of applications, we found out that there were some areas in which ROS could not be applied to. Since the core message passing system runs on TCP/IP, it is not **Real-Time Safe**, and since the core functionalities of ROS took up a substantial amount of space, the **Small Embedded Systems** community also could not adapt this marvellous technology immediately.

Of course, one could argue that with the release of packages like *ros_bridge* and *rosserial* which allows the transfer of data between the host and the device using the USART protocol has definitely made things better. But the problem with this implementation is that a small embedded system(STM32/Arduino) running rosserial is still "technically" not a ROS node. It is more of an edge device, which is just sending data to a larger embedded system for further processing and/or decision making. The ROS developers have always been trying to get ROS to run on smaller target devices, mainly microcontrollers, which interact with the sensors directly. The idea was to eliminate the use of drivers completely, by making the sensor ready for integration right out of the box. 

ROS2 has been developed with the industry-standard message passing system called DDS(Data Distribution Service). DDS has been developed keeping in mind the mission-critical nature of some applications. This was a huge nod to the Real-Time Embedded Systems developers to take a look at the code and to possibly adapt the stack for their future endeavours.
---

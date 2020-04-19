---
layout: post
title: A Real-Time ROS Currated List
---

A good way to start a project is doing a state-of-the-art. Here, we decided to go for a currated list of ROS packages that have real-time features, whether soft, firm or hard. We will not list the ROS2 packages with real-time features, since ROS2 was meant to have at least soft real-time capabilities from day one.

## [realtime_tools](http://wiki.ros.org/realtime_tools)

Contains a set of tools that can be used from a hard realtime thread, without breaking the realtime behavior.

* Maintainer status: maintained
* Maintainer: Bence Magyar <bence.magyarrobotics AT gmail DOT com>, Gennaro Raiola<gennaro.raiola AT iit DOT it>
* Author: Stuart Glaser <sglaser AT willowgarageDOT com>
* License: BSD
* Bug / feature tracker: https://github.comros-controls/realtime_tools/issues
* Source: git https://github.com/ros-controlsrealtime_tools.git (branch: melodic-devel)

## [rtt_lwr](https://rtt-lwr.readthedocs.io/en/latest/)

**rtt_lwr** is a set of components for controlling the Kuka LWR and IIWA at 1Khz. It relies on OROCOS for the real-time part, but also interfaces with ROS so we can use Rviz, MoveIt, ros-control etc.

It has been designed so researchers/Phd Students/Engineers at ISIR can develop generic controllers for light weight robots and seemlessly switch between simulation/real hardware without the need to recompile their code.

* Maintainer status: not maintained
* Maintainers: TBD
* Author: TBD
* Licence: TBD
* Bug / feature tracker: None
* Source: https://github.com/orocos/rtt_ros_control.git

* Additional Infos : [Rock Core](https://github.com/rock-core) may be using the package. Need to investigate.

## [PR2](https://github.com/pr2)

**pr2** is maintained by Open Robotics and uses real-time features for its controller.
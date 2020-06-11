---
layout: post
title: A Real-Time ROS Currated List
feature-img: "img/sample_feature_img_3.png"
---

A good way to start a project is doing a state-of-the-art. Here, we decided to go for a currated list of ROS packages that have real-time features, whether soft, firm or hard. We will not list the ROS2 packages with real-time features, since ROS2 was meant to have at least soft real-time capabilities from day one.

# Real Time and ROS

## Set of packages

### OROCOS

The **OROCOS** Toolchain allows setup, distribution and the building of real-time software components. It is sometimes refered to as ‘middleware’ because it sits between the application and the Operating System. It takes care of the real-time communication and execution of software components.

Basically every ROS function that you might be used to call in regular rosnode has been wrapped for orocos to be Real-Time Safe.

Most used features include :

- Transform the deployer into a ROS node (rtt_rosnode)
- Connect an Orocos port to a ROS topic (rtt_roscomm)
- Connect an Orocos operation to a ROS service (rtt_roscomm)
- Map Orocos Parameters with the ROS parameter server (rtt_rosparam)
- Get the clock from ros (rtt_rosclock)

### List of packages from OROCOS

- **rtt_ros** ROS package import plugin as well aswrapper scripts and launchfiles for using Orocoswith ROS.
- **rtt_rosclock** Realtime-Safe NTP clock measurementand ROS Time structure construction as well as asimulation-clock-based periodic RTT activity.
- **rtt_rosnode** Plugin for ROS node instantiationinside an Orocos program.
- **rtt_rosparam** Plugin for synchronizing ROSparameters with Orocos component properties.
- **rtt_roscomm** ROS message typekit generation and Orocos plugin for publishing and subscribing to ROS topics as well as calling and responding toROS services.
- **rtt_rosdeployment** An RTT service whichadvertises common DeploymentComponent operationsas ROS services.
- **rtt_rospack** Plugin for locating ROS resources.
- **rtt_tf** RTT-Plugin which uses tf to allow RTTcomponents to lookup and publish transforms.
- **rtt_actionlib** RTT-Enabled actionlib actionserver for providing actions from ROS-integratedRTT components.
- **rtt_dynamic_reconfigure** A service plugin thatimplements a dynamic_reconfigure server toupdate properties dynamically during runtime.
- **rtt_ros_msgs** ROS .msg and .srv types for usewith these plugins.
- **rtt_ros_integration** Catkin metapackage for this repository.

## Packages

### [rtt_lwr](https://rtt-lwr.readthedocs.io/en/latest/)

**rtt_lwr** is a set of components for controlling the Kuka LWR and IIWA at 1Khz. It relies on OROCOS for the real-time part, but also interfaces with ROS so we can use Rviz, MoveIt, ros-control etc.

It has been designed so researchers/Phd Students/Engineers at ISIR can develop generic controllers for light weight robots and seemlessly switch between simulation/real hardware without the need to recompile their code.

* Maintainer status: not maintained
* Maintainers: TBD
* Author: TBD
* Licence: TBD
* Bug / feature tracker: None
* Source: https://github.com/orocos/rtt_ros_control.git

* Additional Infos : [Rock Core](https://github.com/rock-core) may be using the package. Need to investigate.

## Toolboxes

### [realtime_tools](http://wiki.ros.org/realtime_tools)

Contains a set of tools that can be used from a hard realtime thread, without breaking the realtime behavior.

Basically, it implements a real-time clock consistent with ROS in order to help you not break real-time constraints.

* Maintainer status: maintained
* Maintainer: Bence Magyar <bence.magyarrobotics AT gmail DOT com>, Gennaro Raiola<gennaro.raiola AT iit DOT it>
* Author: Stuart Glaser <sglaser AT willowgarageDOT com>
* License: BSD
* Bug / feature tracker: https://github.comros-controls/realtime_tools/issues
* Source: git https://github.com/ros-controlsrealtime_tools.git (branch: melodic-devel)

# ROS2 and Real Time

Real-time computing is a key feature of many robotics systems, particularly safety- and mission-critical applications such as autonomous vehicles, spacecrafts, and industrial manufacturing. We are designing and prototyping ROS 2 with real-time performance constraints in mind, since this is a requirement that was not considered in the early stages of ROS 1 and it is now intractable to refactor ROS 1 to be real-time friendly.

The official way to build a real-time linux to use the real-time features of ROS2 is to patch a vanilla kernel with RTPREEMPT Linux.

[Design Guidelines, Real Time ROS2](http://design.ros2.org/articles/realtime_background.html#memory-management)
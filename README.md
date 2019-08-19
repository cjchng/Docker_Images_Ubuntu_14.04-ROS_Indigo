# Docker Images Ubuntu 14.04+ROS Indigo

This Image can use in **Linux OS and windows OS with Installed WSL (Windows Subsystem for Linux) **

1. Pull docker images 

   Pull the images from docker hub using the command:

   - *docker pull anto112/ros_lsd_slam*

2. Build container

   a. To build container in **Linux OS** you can use the command:

   - *docker run -it --privileged=true --net=host -e DISPLAY --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 --name **>name-container<** anto112/ros_lsd_slam /bin/bash*

     

   b. To build container in **windows OS with Installed WSL (Windows Subsystem for Linux)** you must install Xserver such as in here I use [X410](https://token2shell.com/howto/x410/):

   - docker run -it --privileged=true --net=host -e DISPLAY=docker.for.win.localhost:0.0 --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 --name **>name-container<** anto112/ros_lsd_slam /bin/bash

   ***>name-container<** =modify this name with your own

3. Get in to container

   a. If you want to access the container from **Linux OS** use the command:

   - *docker exec -it -e DISPLAY **>name-container<** bash*

   b. If you want to access the container from **windows OS with Installed WSL (Windows Subsystem for Linux)** use the command:

   - docker exec -it -e DISPLAY=docker.for.win.localhost:0.0 **>name-container<** bash

4. Test the image can work

   The easy way to test ROS(Robot Operating System) node is running the turtle simulator. Both  of **Linux OS** of **windows OS with Installed WSL (Windows Subsystem for Linux)** is same. follow this guide to running that using docker container:

   a. starting roscore 

   ​		After you get in terminal of container, typing the comand ***roscore*** . that have function for collection of [nodes](http://wiki.ros.org/Nodes) and programs that are pre-requisites of a ROS-based system. You **must** have a roscore running in order for ROS nodes to communicate .

   b. run turtle simulator

   ​		you just need typing the command:

   - *rosrun turtlesim turtlesim_node*

     that command will launch the user interface of turtle simulator like picture bellow this.

     <img src="Images/2.png" width="550" height="500"/>
     
     

   c. the last is typing command for controller the turtle:

    - *rosrun turtlesim turtle_teleop_key*

      <img src="Images/3.png" width="550" height="500"/>

      

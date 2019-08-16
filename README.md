# Docker Images Ubuntu 14.04+ROS Indigo

1. Pull docker images 

   pull the images from docker hub using the command:

   - *docker pull anto112/ros_lsd_slam*

2. Build container

   to build container you can use the command 

   - *docker run -it --privileged=true --net=host -e DISPLAY --volume /tmp/.x11-unix --env QT_X11_NO_MITSHM=1 --name **>name-container<** anto112/ros_lsd_slam /bin/bash*

     ***>name-container<** =modify this name with your own

3. Get in to container

   - *docker exec -it -e DISPLAY **>name-container<** bash*

4. Test the image can work

   The easy way to test ROS(Robot Operating System) node is running the turtle simulator. follow this guide to running that using docker:

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
   
      

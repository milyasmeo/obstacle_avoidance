# obstacle_avoidance
In this simulation, I'll show how to make a simple obstacle avoidance algorithm running on a simulated env in ROS. 
First of all, you have to install some kind of mobile robot simulator. 
I am using turtlebot3 in gazebo simulation env., running on Ubunutu 18.04 and ROS melodic.
You may use any robot simulator provided it can publish on  '/cmd_vel' topic and can subscribe to '/scan' topic. Any kind of range sensorsm (e.g. ultrasonic, lidar, Radar, RGBD sensors) can be used which publishes range data on  '/scan' topic. 
Obstacle avoisdance alorithm in this simulation does not use map, and robot goes only forward untill it 
encounters any obstacle in front, ledft-side or right-sides.  When a obstacle is perfectly in front, it simply 
stops untill the obstacle is gone/removed. In case of left-side or right-side ostacles, robot takes CW and CCW turnes respectively, 
untill obstacle is beyond given distance-threshold (in our case Threshold=1m). 

How to Run?
1) Open a Terminal, and run: $ roslaunch turtlebot3_gazebo turtlebot3_house.launch
2) Open 2nd Ternimal and Run: $ rosrun obstacle_avoidanc obstacle_avoidance.py

You may put blocks (cube, sphare etc. provided in Gazebo) in front of robot to check that Obstacle Avoidance algorithm is working.

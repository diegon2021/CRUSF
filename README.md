# CRUSF
Files used to run the robot

Ros packages used to run the roboteq motor controller, some files were edited to suit our project
To start the motor controller and PS4 controller run the command:
```
roslaunch roboteq_controller driver.launch
```
this will connect to the bluetooh controller automatically

------------------------------------------------------------------------------------------------------------------------------------------------------


The Hokuyo LIDAR ip address is: 192.168.5.10
To start it, you first need to set the ethernet profile to have deafult route of 192.168.5.10
On the USF Collaborative Robot, the profile s already created it is just required to select it from the setting tab. The profile name is hokuyo
To star scanning run the following command:
```
rosrun urg_node urg_node _ip_address:="192.168.5.10"
```

------------------------------------------------------------------------------------------------------------------------------------------------------



To start mapping we are using the Hector SLAM algorithm, to run write the following command:
```
roslaunch hector_slam_launch tutorial.launch
```
This will launch RVIZ where the area is going to be mapped using the /scan topic from the LIDAR


------------------------------------------------------------------------------------------------------------------------------------------------------


To save the map go to the maps directory:
```
cd catkin_ws/maps/
```
If you have ros map_server, just run the following command to save the map:
```
rosrun map_server map_saver -f [name of the Map here]
```
To load the map back to RVIZ, you will first need to have it open and run the command:
```
rosrun map_server map_server [name of the Map here]
```
Or you can simply just save a screenshot of the map from RVIZ if it will not be loaded again

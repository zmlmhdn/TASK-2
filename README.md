# Commands used in terminal
## Launching simulation

1. Gazebo
   $ export TURTLEBOT3_MODEL=waffle

   $ ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

2. Teleop for movement of the robot in simulation
    $ ros2 run turtlebot3_teleop teleop_keyboard
   
3. Rviz2
    $ ros2 launch turtlebot3_bringup rviz2.launch.py

## Inspecting message structure
$ ros2 interface show geometry_msgs/msg/Twist

$ ros2 interface show sensor_msgs/msg/LaserScan

## Record simulation data
- record the robot movement command:
$ ros2 bag record /scan /odom /cmd_vel

- the simulation is done by moving the robot for 2 minutes randomly using the WASDX keybinds
- while moving, data is explored which are:

$ ros2 topic list

$ ros2 topic info /cmd_vel

$ ros2 topic echo /odom --once

$ ros2 topic hz /scan

- these topics were inspected before and after moving the robot
- the results can be viewed in the png file and txt above

## Replay simulation data
$ ros2 bag play <bag_name>
- 

$ ros2 bag info <bag_name>

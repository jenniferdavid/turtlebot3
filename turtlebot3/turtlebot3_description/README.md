1. roscore

2. ssh robot1@robot1IPaddress

ROS_NAMESPACE=tb3_0 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:=tb3_0 set_lidar_frame_id:=tb3_0/base_scan

3. ssh robot2@robot2IPaddress

ROS_NAMESPACE=tb3_1 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:=tb3_1 set_lidar_frame_id:=tb3_1/base_scan

4. ROS_NAMESPACE=tb3_0 roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

5. ROS_NAMESPACE=tb3_1 roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

6. ROS_NAMESPACE=tb3_0 roslaunch turtlebot3_slam turtlebot3_gmapping.launch set_base_frame:=tb3_0/base_footprint set_odom_frame:=tb3_0/odom set_map_frame:=tb3_0/map

7. ROS_NAMESPACE=tb3_1 roslaunch turtlebot3_slam turtlebot3_gmapping.launch set_base_frame:=tb3_1/base_footprint set_odom_frame:=tb3_1/odom set_map_frame:=tb3_1/map

8. roslaunch turtlebot3_gazebo multi_map_merge.launch

9. rosrun rviz rviz -d `rospack find turtlebot3_description`/rviz/multi_turtlebot3_slam.rviz 

10. rosrun map_server map_saver -f ~/map















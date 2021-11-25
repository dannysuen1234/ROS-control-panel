# ROS-control-panel
The purpose of this control panel is to develop a GUI for users who do not have background in ROS. With this control panel, the users can perform SLAM, map modification, navigation, record a self_defined path and use the defined path for navaigtion without typing ros commands.

In order to use this panel, you are assumed to have the package for SLAM, map modification, navigation. The scripts to define a path and use the path for navigation are included in this repository. 

Customize your own panel:

There are few vairables you can change to customize your application.

![image](https://user-images.githubusercontent.com/79799975/141095392-bdc16af4-68a7-4782-8997-99cd959c90a0.png)

gazebo_package: the package where you store the launch file for the SLAM application__
gazebo_launch: the launch file that should contain everything needed for SLAM (gazebo world, robot, rviz)__
navigation_package: the package where you store the launch file for the navigation application__
navigation_launch: the launch file that should contain everything needed for navigation(gazebo world, robot, map used for navigation, navigation algorithm)__
move_base_package: the package where you store the launch file for the move base navigation__
move_base_lanch: the launch file that should contain everything needed for move_base_navigation (gazebo world, robot, move base navigation algorithm)__
rviz_package: the package where you store the rviz launch file__
rviz_launch: launch the rviz with the configuration in this file__
map_path_pmg: the pmg file where you will save the map generated by SLAM in this path__
map_path_yaml: the yaml file where you will save the map generated by SLAM in this path__
save_map_path: usually the map generated by SLAM will need some modification before use. This path is where you will save the modified path. __
good_math_path_yaml:  This is the yaml file where you store the modified map in this path.__


ros control panel.py
procedure
In the terminal, run the command python 'ros control panel.py'

You should see a panel like this:

![image](https://user-images.githubusercontent.com/79799975/141094604-b158af6b-d192-4092-8277-1172d0c4f8e7.png)

Panel buttons explanation

"Start Task 1 SLAM": start the SLAM application in 'gazebo_package' with launch file 'gazebo_launch'
"Save map": Save the map generated by SLAM to the path 'save_map_path'
"Edit map": Edit the map you saved 
"Start task2 navigation" start the navigation application in 'navigation_package' with launch file 'navigation_launch'
"Point 1" to "point 5": navigate the robot to point 1 to point 5  after starting "Start task2 navigation"
"Use good map": Use the modified map for navigation
"Use bad map" use the map generated by SLAM directly for navigation
"Move base demo": start the move base navigation application in "move_base_package" with "move_base_launch"
"Open RVIZ": start the configured RVIZ in "rviz_package" with "rviz_launch"
"record path 1" this will start the python script "tf_listener.py". You can move the robot around and the path will be recorded for future use.
"stop recording": this will terminate the script "tf_listener.py". The path will be saved.
"Use path 1" this will start the robot navigation using the defined path
"Quit": this will terminate all launch application 

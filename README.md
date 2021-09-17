# CSDS 373 Lab 2: RVIZ and URDF
## By Kris Zhao (kxz167)

### Development:
Preliminary developement was done in Ros Melodic for Windows 10.\
Final developement was done in Ubuntu 18.04 running natively on hardware with Ros Melodic for Ubuntu.

### Information:
Package name:
```
navvis_descriptions
```

URDF Files:
- navvis.urdf - urdf file before upgrade to xacro for wheel creation (does not include wheels or packaged sensors).
- navvis.xacro - Completed xacro file for running the robot.
- navvis_urdf_from_xacro.urdf - converted file for checking urdf (outdated).

#### Project directory:
- navvis_descriptions (Will be named `csds373_f21_kxz167_l2_navvis_descriptions` due to github clone.)
    - config
        - config.rviz
    - urdf
        - navvis.urdf
        - navvis.xacro
        - navvis_urdf_from_xacro.urdf
    -

### Running:
Confirm ROS is available in the shell:
```
source /opt/ros/melodic/setup.bash
```
Download the project to:
```
catkin_ws/src/
```

From the `catkin_ws` directory, build the package (I just build all packages):
```
catkin_make
```

Source the devel:
```
source devel/setup.bash
```

Running the visualization:
```
roslaunch navvis_description navvis_description.launch [options
```
NOTE: depending on other package names from other students, pacakge direction may not work properly. Make sure to clear out other packages named navvis_description. In the future I will make sure and add my student ID to the package name.\
\
Options:
- `use_xacro:= [true/false]` - Use the xacro file (true) or the urdf file (false : default)
- `jsp_gui:= [true/false]` - Utilize the Joint State Processor Gui to command wheels (true : default) or "render" vehicles through single joint msg (false)

### Notes:
- You will need to rename the downloaded folder to navvis_descriptions in order to match the directory naming scheme due to github package naming conventions. In terms of running, this does not seem to impact running the code.
- For the full functionality, the `use_xacro:=true` flag should be used. Utilizing the old URDF file will not show the completed robot.
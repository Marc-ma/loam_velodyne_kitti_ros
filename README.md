# loam_velodyne_kitti_ros
This package is a modified copy of [ROS loam_velodyne](http://docs.ros.org/indigo/api/loam_velodyne/html/files.html) to work with the KITTI dataset.
 
Main changes have been done in:
 
scanRegistration.cpp renamed to scanRegistrationKittiROS.cpp

where at the end of this file the KITTI Dataset is published by reading the .bin files and converting it to point cloud data.
 
Also, transformToEnd() and transformToStart() functions have been modified since the KITTI Dataset is distorsion free.

The separation of the Velodyne HDL-64's rings have been done according to [laboshinl's code](https://github.com/laboshinl/loam_velodyne)

How to build:

```
$ cd catkin_ws
$ catkin_make
```
Running:
```
$ roslaunch loam_velodyne_kitti_ros loam_velodyne_kitti_ros.launch 
$ rosrun loam_velodyne_kitti_ros record_loam_odometry.py 
$ ./plot_trajectory LOAMTrajectory.txt
```

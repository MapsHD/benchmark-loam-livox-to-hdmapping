# loam-livox-converter



## Intended use 

This small toolset allows to integrate SLAM solution provided by [loam-livox](https://github.com/hku-mars/loam_livox/) with [HDMapping](https://github.com/MapsHD/HDMapping).
This repository contains ROS  workspace that :
  - submodule to tested revision of Loam livox
  - a converter that listens to topics advertised from odometry node and save data in format compatible with HDMapping.


## Building

Clone the repo
```shell
mkdir -p /test_ws/src
cd /test_ws/src
git clone https://github.com/marcinmatecki/loam-livox-to-hdmapping --recursive
cd ..
catkin_make
```

## Usage - data SLAM:

Prepare recorded bag with estimated odometry:

In first terminal record bag:
```shell
rosbag record /velodyne_cloud_registered /aft_mapped_to_init"
```

and start odometry:
```shell 
cd /test_ws/
source ./install/setup.sh # adjust to used shell
For launch,check https://github.com/hku-mars/loam_livox/
```

## Usage - conversion:

```shell
cd /test_ws/
source ./install/setup.sh # adjust to used shell
rosrun loam-to-hdmapping listener <recorded_bag> <output_dir>
```




## Modified for build


**Changes made:**

 
   ```
  File:

  test_ws/src/loam-livox-to-hdmapping/src/loam_livox/source/read_camera.cpp

    cap.set(CV_CAP_PROP_SETTINGS, 1); //opens camera properties dialog
    cap.set( CV_CAP_PROP_FRAME_WIDTH, 320 );
    cap.set( CV_CAP_PROP_FRAME_HEIGHT, 240 );

    CHANGED TO:

    cap.set(cv::CV_CAP_PROP_SETTINGS, 1); //opens camera properties dialog
    cap.set( cv::CV_CAP_PROP_FRAME_WIDTH, 320 );
    cap.set( cv::CV_CAP_PROP_FRAME_HEIGHT, 240 );

    test_ws/src/loam-livox-to-hdmapping/src/loam_livox/source/laser_feature_extractor.hpp

    #include <opencv/cv.h>

    CHANGED TO:

    #include <opencv2/opencv.hpp>
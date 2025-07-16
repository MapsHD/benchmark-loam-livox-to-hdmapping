# loam-livox-converter




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





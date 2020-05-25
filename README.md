# OpenVSLAM-mod

This is a modification of openVSLAM I have made for the embedded machine learning course at Jönköping university. 

To install do the following:
  1. Clone the repository
  2. Navigate to the cloned directory and run: git submodule update --init --recursive
  3. Open OpenVSLAM.sln in visual studio (preferrably 2017).
  4. Click build solution. (you may need to change opencv to use windows 10 sdk by right clicking on the project in visual studio and         changing the field called "Windows SDK")
  
If you have trouble building the project I have provided a pre-built application here: https://gofile.io/d/6T69wV

When you have the exe files you need to navigate (if you built them from the repo they should be located in <repo>/x64/Release) to them and  run a command like this: ./run_camera_slam -v C:\openvslam-build-vs\orb_vocab.dbow2 -c C:\openvslam-build-vs\config.yaml --map-db camera_map.msg -n 0. Where -v is the orb vocabulary file, I have provided one in the repo. -c is the config file for your camera, to generate a config file you need to calibrate your camera, I have provided the code I used to calibrate mine: https://github.com/famattsson/cam-calibration. --map-db is the location to save the map to. -n is the index of the camera you wish to use. 

Alternatively, if you want to load a map you can run a command like this ./run_camera_localization -v C:\openvslam-build-vs\orb_vocab.dbow2 -c C:\openvslam-build-vs\config.yaml --map-db. Where most of the options are the same as before but --map-db instead indicates which map to load. I have provided several maps generated from my own SLAM sessions in the repo.

---
title: ‎ 
subtitle: ‎ 
layout: page
show_sidebar: false
hide_footer: true
menubar_toc: true
hero_height: is-medium
hero_image: /img/iccv/Mul.gif
---

# 🎉 Welcome to ICCV'23 Sensor-Fusion SLAM Challenge! 🎉

# Challenge

In this track, we exclusively offer access to high-quality **sensor-fusion** datasets sourced from SubT-MRS. These datasets encompass various challenging conditions such as **"lighting changes, darkness, smoke, self-similar environments and more"**.


Three separate awards will be given for each track.
Your SLAM performance in <b>the Sensor Fusion track will not impact</b> the scores in other tracks.
Join us now to become a vital part of cutting-edge advancements in robotics and sensor fusion! 🤖💡 Let your expertise shine in this thrilling competition!


## SubT-MRS Datasets

- <b> Multiple Modalities: </b>
Our dataset includes hardware time-synchronized data from 4 RGB cameras, 1 LiDAR, 1 IMU, and 1 thermal camera, providing diverse and precise sensor inputs.

- <b> Diverse Scenarios: </b>
    Collected from multiple locations, the dataset exhibits varying environmental setups, encompassing indoors, outdoors, mixed indoor-outdoor, underground, off-road, and buildings, among others.

- <b> Multi-Degraded: </b>
   By incorporating multiple sensor modalities and challenging conditions like fog, snow, smoke, and illumination changes, the dataset introduces various levels of sensor degradation.

- <b> Heterogeneous Kinematic Profiles:</b>
  The SubT-MRS Dataset uniquely features time-synchronized sensor data from diverse vehicles, including RC cars, legged robots, drones, and handheld devices, each operating within distinct speed ranges. 

   File structure:  (@YuanJun)

    ```
    Multi_Modality_Track
    ├── Lidar_Visual_IMU
    │   ├── Multi_Floor
    │   │   ├── rosbags
    │   │   │   ├── raw_sensor_data
    │   │   │   │   └── raw_data_yyyy-mm-dd-hh-mm-ss[...].bag
    │   │   │   └── super_odometry_results
    │   │   │       └── so_result_yyyy-mm-dd-hh-mm-ss[...].bag
    │   │   ├── folders
    │   │   │   ├── raw_sensor_data
    │   │   │   │   ├── cam_0
    │   │   │   │   │   ├── {...}.png
    │   │   │   │   │   └── timestamps.txt
    │   │   │   │   ├── imu
    │   │   │   │   │   └── imu_data.csv
    │   │   │   │   ├── lidar
    │   │   │   │   │   ├── {...}.las
    │   │   │   │   │   └── timestamps.txt
    │   │   │   │   └── tf
    │   │   │   │       └── tf_data.csv
    │   │   │   └── super_odometry_results
    │   │   │       └── ...
    │   │   ├── extrinsics.yaml
    │   │   └── intrinsics.yaml
    │   ├── Sensor_Drop
    │   │   └── ...
    │   └── Long_Corridor
    │       └── ...
    └── Visual_Thermal_IMU
        ├── Flash_Light
        │   ├── rosbags
        │   │   ├── raw_sensor_data
        │   │   │   └── raw_data_yyyy-mm-dd-hh-mm-ss[...].bag
        │   │   └── super_odometry_results
        │   │       └── so_result_yyyy-mm-dd-hh-mm-ss[...].bag
        │   ├── folders
        │   │   ├── raw_sensor_data
        │   │   │   ├── cam_0
        │   │   │   │   ├── {...}.png
        │   │   │   │   └── timestamps.txt
        │   │   │   ├── imu
        │   │   │   │   └── imu_data.csv
        │   │   │   ├── tf
        │   │   │   │   └── tf_data.csv
        │   │   │   └── thermal
        │   │   │       ├── {...}.png
        │   │   │       └── timestamps.txt
        │   │   └── super_odometry_results
        │   │       └── ...
        │   ├── extrinsics.yaml
        │   └── intrinsics.yaml
        ├── Smoke_Room
        │   └── ...
        └── Outdoor_Night
            └── ...
    ```


<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>



## Tartan Air Dataset

   This benchmark is based on the [TartanAir dataset](http://theairlab.org/tartanair-dataset/), which is collected in photo-realistic simulation environments based on the AirSim project. A special goal of this dataset is to focus on the challenging environments with changing light conditions, adverse weather, and dynamic objects. The four most important features of our dataset are:

   - **Large size diverse realistic data.** We collect the data in diverse environments with different styles, covering indoor/outdoor, different weather, different seasons, urban/rural.
   - **Multimodal ground truth labels.** We provide RGB stereo, depth, optical flow, and semantic segmentation images, which facilitates the training and evaluation of various visual SLAM methods. 
   - **Diversity of motion patterns.**  Our dataset covers much more diverse motion combinations in 3D space, which is significantly more difficult than existing datasets.
   - **Challenging Scenes.** We include challenging scenes with difficult lighting conditions, day-night alternating, low illumination, weather effects (rain, snow, wind and fog) and seasonal changes.Please refer to the TartanAir Dataset and the paper for more information. 

   File structure: 

    ```
    mono
    |
    --- ME000                             # monocular easy trajectory 0 
    |       |
    |       ---- 000000.png          # RGB image 000000
    |       ---- 000001.png          # RGB image 000001
    |       .
    |       .
    |       ---- 000xxx.png           # RGB image 000xxx
    |
    +-- ME001                             # monocular easy trajectory 1 
    .
    .
    +-- ME007                            # monocular easy trajectory 7 
    |
    +-- MH000                            # monocular hard trajectory 0 
    .
    .
    |
    +-- MH007                            # monocular hard trajectory 7
    ```

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>


![GIF Figure 1](img/slam_challenge/abandonedfactory.gif) ![GIF Figure 2](img/slam_challenge/gascola.gif) \\
![GIF Figure 3](img/slam_challenge/hospital.gif) ![GIF Figure 4](img/slam_challenge/jananesealley.gif)



## Download (@Tianhao @WenShan )

Click [here](dummy) to download the testing data for visual-inertial track. (Size: 7.65 GB)

| Name | Source  | Location  | Robot |Sensor | Description | Trajectory | Duration  | Size  |  Video | Download Link|
|---|-----------|---------|-----------|-----------|------------|-----------|-------------|-----------|---------------|--------------|
|Multi_Floor|SubT-MRS|Hawkins|SP1|Lidar,RGB,IMU|Multi Floor|270|480|21.2G|[link](dummy)| [Baidu](dummy) [google](dummy)          |
|Long_Corridor|SubT-MRS|Hawkins|RC2|Lidar,RGB,IMU|Multi Floor|616.45|332|14.6G|[link](dummy)| [Baidu](dummy) [google](dummy)          |
|SensorDrop1|SubT-MRS|Mill19|RC3|Lidar,RGB,IMU|Block Lidar|307.55|677|17.1G|[link](dummy)| [Baidu](dummy) [google](dummy)                           |
|SensorDrop2|SubT-MRS|Mill19|RC3|Lidar,RGB,IMU|Block Visual|186.02|359|19.8G|[link](dummy)| [Baidu](dummy) [google](dummy)              |
|SmokeRoom|SubT-MRS|Hawkins|RC7|RGB,Thermal,IMU|Visual Degraded|104.84|418|20G|[link](dummy)| [Baidu](dummy) [google](dummy)              |
|OutdoorNight|SubT-MRS|Hawkins|RC7|RGB,Thermal,IMU|Visual Degraded|254.03|484|22.9G|[link](dummy)|  [Baidu](dummy) [google](dummy)               |
|FlashLight|SubT-MRS|Hawkins|RC7|RGB,Thermal,IMU|Visual Degraded|147.75|279|13G|[link](dummy)|  [Baidu](dummy) [google](dummy)               |



## Evaluation (@ Wenshan)
The submission will be ranked based on completeness of the trajectory as well as on the position accuracy (ATE).

1. The following metrics will be used to evaluate the SLAM algorithms' performance:

For a known ground truth trajectory ME000_gt.txt and an estimated trajectory ME000_est.txt, we calculate the translation and rotation error based on the normalized Relative Pose Error similar to the KITTI dataset. Different from KITTI, we compute translational and rotational errors for all possible subsequences of length (5, 10, 15, ...,40) meters.  The translational error and rotational error are then combined to the final score:  , where we use  to balance the two errors, because the average rotation speed (in degree) is 7 times bigger than the average translation speed on our dataset. 

Due to the scale ambiguity of the monocular image, a global scale factor is calculated before the error computation. 

2. Download the evaluation tools. (TODO)

    Download the tartanair_tools repository, and follow the instruction here. 


## Submit the results. 

### Prepare the trajectory
For each of the 5 trajectories of **sensor-fusion track**, you need to compute the **poses in IMU coordinate frame**, and save them in the text file with the name sequnce_name.txt. Put all 5 files into a zip file with the following structure: 

```
    visual_inertial_track.zip
    |
    --- ME000.txt                             # result file for the trajectory ME000 
    --- ME001.txt                             # result file for the trajectory ME001
    |          ..
    |          ..
    --- ME007.txt                             # result file for the trajectory ME007
    |       
    --- MH000.txt                             # result file for the trajectory MH000
    --- MH001.txt                             # result file for the trajectory MH001
    |          ..
    |          ..
    --- MH007.txt                             # result file for the trajectory MH007 
```
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

The text file should have the following format: 

```
# timestamp_s tx ty tz qx qy qz qw
1.403636580013555527e+09 0.0 0.0 0.0 0.0 0.0 0.0 0.0

```

<br>
<br>
<br>
<br>
<br>

The camera pose file should have the same format as the ground truth file in the training data. It is a text file containing the translation and orientation of the camera in a fixed coordinate frame. Note that our automatic evaluation tool expects the estimated trajectory to be in this format. 

- Each line in the text file contains a single pose.
- The number of lines/poses must be the same as the number of image frames in that trajectory. **(TODO: do we need this assumption? @wenshan)**  
- The format of each line is 'tx ty tz qx qy qz qw'. 
- tx ty tz (3 floats) give the position of IMU sensor to the world origin in the world frame.
- qx qy qz qw (4 floats) give the orientation of IMU in the form of a unit quaternion with respect to the world frame. 
- The trajectory can have an arbitrary initial position and orientation. However, we are using the IMU frame to define the motion. That is to say, the x-axis is pointing to forward, the y-axis is pointing left, the z-axis is pointing up.

### Submit in Gradescope  (@wenshan)

- Todo: provide the instruction of submission

##  🎉Sensor-Fusion Leaderboard 🎉

| Rank | Algorithm       | ATE (m)  | RPE (%)  | Use Loop Closure | Learning/Traditional|sensor | Run-time (ms) | Memory (MB) |
|------|-----------------|----------|----------|------------------|---------------------|------------------|---------------|------------|
| 1    | Algorithm A     | 0.15     | 0.85     | True             | 90.2                | Visual, IMU              | 28.3          | 235.5      |
| 2    | Algorithm B     | 0.21     | 1.20     | False            | 89.1                | Visual, IMU             | 35.6          | 281.8      |
| 3    | Algorithm C     | 0.28     | 1.55     | False            | 85.6                | Visual, IMU            | 43.2          | 320.1      |
| 4    | Algorithm D     | 0.35     | 2.01     | False            |  82.4               | Visual, IMU              | 50.8          | 352.5      |
| 5    | Algorithm E     | 0.41     | 2.45     | False            | 79.8                | Visual, IMU            | 58.1          | 389.7      |

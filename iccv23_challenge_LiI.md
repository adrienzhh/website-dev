---
title: ‎ 
subtitle: ‎ 
layout: page
show_sidebar: false
menubar_toc: true
hide_footer: true
hero_height: is-medium
hero_image: /img/iccv/Lil.gif
---

# 🎉 Welcome to ICCV'23 LiDAR-Inertial SLAM Challenge! 🎉

In the Lidar-inertial track, we exclusively offer access to high-quality **LiDAR-inertial** datasets sourced from SubT-MRS and TartanAir. These datasets encompass various challenging conditions such as **"multi-floor,long corridor, self-similar environments and more"** providing a test from **simulation to real-world**. For the other two tracks, see here: [Visual-Inertial SLAM Challenge](https://superodometry.com/iccv23_challenge_VI) and [Sensor Fusion SLAM Challenge](https://superodometry.com/iccv23_challenge_Mul).

Seize this chance to demonstrate your skills and compete among the finest in the field!

Three separate awards will be given for each track.
Join us now to become a vital part of cutting-edge advancements in robotics and sensor fusion! 🤖💡 Let your expertise shine in this thrilling competition!

<span style="font-size:1.3em;">If you have any question, please do not hesitate to post issues on this [github website](https://github.com/water-horse/ICCV2023_SLAM_Challenge.git). We would love to hear from your feedback! Every post will be responded with no spared effort within 36 hours.<span>

File structure: 

```
rosbag
├── TartanAir_lidar_{places ...}_noise0.bag
└── SubT_MRS_{trajectory names ...}_{robot types ...}.zip
    └── (zipped) raw_data_{...}yyyy-mm-dd-hh-mm-ss{...}.bag

folder
├── TartanAir_lidar_{places ...}.zip
│   ├── (zipped) imu
│   │   └── [acc/gyro/imu/imu_time].[npy/txt]
│   └── (zipped) lidar
│       ├── {...}_lcam_front_lidar.ply
│       └── timestamps.txt
└── SubT_MRS_{trajectory names ...}_{robot types ...}.zip
    ├── (zipped) imu
    │   └── imu_data.csv
    ├── (zipped) lidar
    │   ├── {...}.las
    │   └── timestamps.txt
    └── (zipped) tf
        └── tf_data.csv
```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## SubT-MRS Datasets

- <b> Multiple Modalities: </b>
Our dataset includes hardware time-synchronized data from 4 RGB cameras, 1 LiDAR, 1 IMU, and 1 thermal camera, providing diverse and precise sensor inputs.

- <b> Diverse Scenarios: </b>
    Collected from multiple locations, the dataset exhibits varying environmental setups, encompassing indoors, outdoors, mixed indoor-outdoor, underground, off-road, and buildings, among others.

- <b> Multi-Degraded: </b>
   By incorporating multiple sensor modalities and challenging conditions like fog, snow, smoke, and illumination changes, the dataset introduces various levels of sensor degradation.

- <b> Heterogeneous Kinematic Profiles:</b>
  The SubT-MRS Dataset uniquely features time-synchronized sensor data from diverse vehicles, including RC cars, legged robots, drones, and handheld devices, each operating within distinct speed ranges. 

## TartanAir Dataset
   This benchmark is based on the [TartanAir dataset](http://theairlab.org/tartanair-dataset/), which is collected in photo-realistic simulation environments based on the AirSim project. A special goal of this dataset is to focus on the challenging environments with changing light conditions, adverse weather, and dynamic objects. The four most important features of our dataset are:

   - **Large size diverse realistic data.** We collect the data in diverse environments with different styles, covering indoor/outdoor, different weather, different seasons, urban/rural.
   - **Multimodal ground truth labels.** We provide RGB stereo, depth, optical flow, and semantic segmentation images, which facilitates the training and evaluation of various visual SLAM methods. 
   - **Diversity of motion patterns.**  Our dataset covers much more diverse motion combinations in 3D space, which is significantly more difficult than existing datasets.
   - **Challenging Scenes.** We include challenging scenes with difficult lighting conditions, day-night alternating, low illumination, weather effects (rain, snow, wind and fog) and seasonal changes.Please refer to the TartanAir Dataset and the paper for more information. 

   Folder structure inside the Tartan Air dataset: 

```
    lidar_envname
    ├── lidar                                   # LiDAR folder
    │   ├── timestamps.txt                      # LiDAR timestamp
    │   ├── 000000_lcam_front_lidar.png         # RGB LiDAR 000000
    │   ├── 000001_lcam_front_lidar.png         # RGB LiDAR 000001
    │   ├── ... ...
    │   └── 000xxx_lcam_front_lidar.png         # RGB LiDAR 000xxx
    │
    └── imu                                     # IMU folder
        ├── acc.npy                             # IMU acceleration
        ├── acc.txt                             # IMU acceleration
        ├── gyro.npy                            # IMU gyroscope
        ├── gyro.txt                            # IMU gyroscope
        ├── imu.npy                             # IMU acceleration and gyroscope
        ├── imu.txt                             # IMU acceleration and gyroscope
        ├── imu_time.npy                        # IMU timestamp
        └── imu_time.txt                        # IMU timestamp
```

<!-- 
![GIF Figure 1](img/slam_challenge/abandonedfactory.gif) ![GIF Figure 2](img/slam_challenge/gascola.gif) \\
![GIF Figure 3](img/slam_challenge/hospital.gif) ![GIF Figure 4](img/slam_challenge/jananesealley.gif) -->
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Download 

<span style="font-size:1.3em;">ROS bag format:&emsp;**[Google](https://drive.google.com/drive/folders/1hHCsnc-gANmK6Oox-Im3hqRwsGGaJIuJ)** Baidu</span>  
<span style="font-size:1.3em;">Folder format:&ensp;&ensp;&ensp;&nbsp;&nbsp;**[Google](https://drive.google.com/drive/folders/1zVG63JVmRCWSpTCe0F2iOb-E00NaS1JK)** Baidu</span>

| Name | Source  | Location  | Robot |Sensor | Description |  Trajectory Length(m)| Duration (s) | Video | Calibration (Extrinsics) |
|---|-----------|---------|-----------|-----------|------------|-----------|-----------|---------------|--------------|
| Final_Challenge_UGV1 |  SubT-MRS       |         |     UGV1      |    LiDAR,IMU       | Geometry Degraded          |  441.86         |  1600           |[link](https://youtu.be/7lxR0XIwdcM)| [Google](https://drive.google.com/file/d/1jIxqeVk4i3Kj4OD-M8v3C4Bwz9m3d10d/view?usp=drive_link) Baidu |
| Final_Challenge_UGV2 |  SubT-MRS       |         |     UGV2      |    LiDAR,IMU       | Geometry Degraded          |  493.67         |  3390           |[link](https://youtu.be/7lxR0XIwdcM)| [Google](https://drive.google.com/file/d/1aeEVNv6lmpOsVodTfsrDyQwJcCsdHqcb/view?usp=drive_link) Baidu |
| Final_Challenge_UGV3 |  SubT-MRS       |         |     UGV3      |    LiDAR,IMU       | Geometry Degraded          |  593.79         |  1714           |[link](https://youtu.be/7lxR0XIwdcM)| [Google](https://drive.google.com/file/d/1J9MvUTH3-qqNHSRo93m6eluty7o7v1uy/view?usp=drive_link) Baidu |
| Urban_Challenge_UGV1 |  SubT-MRS       |         |     UGV1      |    LiDAR,IMU       | Geometry Degraded          |  124.92         |  513            |[link](https://youtu.be/UGPbnyaStjM)| [Google](https://drive.google.com/file/d/1UHw3s1ab073opa8-0xHzIe-ouULT90pH/view?usp=sharing) Baidu |
| Urban_Challenge_UGV2 |  SubT-MRS       |         |     UGV2      |    LiDAR,IMU       | Geometry Degraded          |  1377.37        |   3120          |[link](https://youtu.be/UGPbnyaStjM)| [Google](https://drive.google.com/file/d/1rNPndrHyPnbsLzG1BksghtwS2AWSsh4_/view?usp=sharing) Baidu |
| Laurel_Cavern        |  SubT-MRS       |         |     Handheld  |    LiDAR,IMU       | Underground Cave           |  490.46         |   960           |[link](https://youtu.be/QYLY2Zc3j1w)| [Google](https://drive.google.com/file/d/1l7UYUVfygY3j1yHzsuovpdHnIClTfKkP/view?usp=sharing) Baidu |
| Lidar_factory       |  TartanAir       |         |  Virtual Sensors | LiDAR,IMU       | Snow                       |  640            |   160.7         |                                    | [Google](https://drive.google.com/file/d/1fyS2Y8QM91VNgPvq7_yngPl1Tm-oaF6M/view?usp=drive_link) Baidu |
| Lidar_ocean         |  TartanAir       |         |  Virtual Sensors | LiDAR,IMU       | Dynamic Objects            |  425            |   127.5         |                                    | [Google](https://drive.google.com/file/d/1fyS2Y8QM91VNgPvq7_yngPl1Tm-oaF6M/view?usp=drive_link) Baidu |
| Lidar_sewerage      |  TartanAir       |         |  Virtual Sensors | LiDAR,IMU       | Geometry Degraded          |  426            |   131.0         |                                    | [Google](https://drive.google.com/file/d/1fyS2Y8QM91VNgPvq7_yngPl1Tm-oaF6M/view?usp=drive_link) Baidu |


## Bonus Tracks

🚀 We also provide 3 extra datasets from   [Sensor Fusion Challenge](/iccv23_challenge_Mul) as bonuses in the competition. 
You will get **extra scores** if you test your algoithm on Bonus Track and submit the results to us. 

<!-- **Please note that the results obtained from the Bonus track will not be factored into the final scoring for the LiDAR-inertial track.** 
The intention behind this separation is to allow participants ample time for fine-tuning their algorithms without the added pressure of immediate scoring.

Nonetheless, it is mandatory for all participants to provide the results from the Bonus track to complete their entry in the lidar-inertial track competition. 
This will aid in a comprehensive evaluation of the algorithms and showcase their adaptability to diverse and complex datasets. -->


| Name | Source    | Location  | Robot     |Sensor     | Description | Trajectory | Duration  |  Video | Calibration (Extrinsics) | Calibration (Intrinsics) |
|------|-----------|-----------|-----------|-----------|-------------|-----------|-------------|-----------|---------------|--------------|
|Long_Corridor  |SubT-MRS|Hawkins|RC2     |RGB,LiDAR IMU|Lidar Degraded|616.45|332|[link](https://youtu.be/prmBxGRGwNY)| [Google](https://drive.google.com/file/d/1bB3jfEJeTf_XoLUHKOaxCNF_MCkiQTol/view?usp=drive_link) Baidu | [Google](https://drive.google.com/file/d/10rv5dg5un7kUveTPS3XBx8IuIYGg9r2h/view?usp=drive_link) Baidu |
|Multi_Floor    |SubT-MRS|Hawkins|SP1|RGB,LiDAR,IMU|Lidar Degraded|270|480|[link](https://youtu.be/QcHjVLlsyXE)| [Google](https://drive.google.com/file/d/1BV87D60W35UGzIaHjKD64c_J1G0U70jf/view?usp=drive_link) Baidu | [Google](https://drive.google.com/file/d/1uH4wFmLeQNrIGlsUsO--PQuyEIOSOGvR/view?usp=drive_link) Baidu |
|Block_LiDAR    |SubT-MRS|Hawkins|SP1|RGB,LiDAR,IMU|Lidar Degraded|307.55|677|[link](https://youtu.be/2r4Z1XKTJHs)| [Google](https://drive.google.com/file/d/1NscQVVsQc_CN-16O_VLpLQnmTWgBmf93/view?usp=drive_link) Baidu | [Google](https://drive.google.com/file/d/1zCqwibpnmJ6I9lv29OUEnjyK2SxN4TbV/view?usp=drive_link) Baidu |

## Evaluation 
The submission is evaluated based on Absolute Trajectory Error (ATE) and Relative Pose Error (RPE). Specifically, The root-mean-square error (RMSE) of ATE and RPE of every trajectory in the lidar inertial track and its bonus track will be evaluated. The final score for a submitted trajectory will be assigned according to the following rule. 

$$
\begin{aligned}
Score_{ATE,RPE} = \ 20 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ RMSE \le 1.0 \ m \\
10 \ \ \ \ \ 1.0 \ m < RMSE \le 2.0 \ m \\
6 \ \ \ \ \ 2.0 \ m < RMSE \le 3.0 \ m \\
5 \ \ \ \ \ 3.0 \ m < RMSE \le 4.0 \ m \\
3 \ \ \ \ \ 4.0 \ m < RMSE \le 5.0 \ m \\
1 \ \ \ \ \ 5.0 \ m < RMSE \le 6.0 \ m \\
0 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ RMSE > 6.0 \ m \\
\end{aligned}
$$

What's more, we will also evaluate the trajectory based on a velocity error (VE) metric. VE is calculated by measuring the velocity difference sampled at a fixed frequency between the submitted trajectory and our groundtruth trjectory. The velocity of your submitted trajectory will be calculated by performing a B-spline interpolation and approximating the instant velocity by the average velocity in short time intervals. As a substitution, you can also submit a velocity file (instructions for this is coming soon). At every sampled point, the velocity difference will be transformed to a score according to the following rule. The RMSE of the per-point scores will be calculated to obtain the final VE score. 

$$
\begin{aligned}
Score_{point_i} = \ 20 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ error_{point_i} \le 0.5 \ m/s \\
10 \ \ \ \ \ 0.5 \ m/s < error_{point_i} \le 1.0 \ m/s \\
6 \ \ \ \ \ 1.0 \ m/s < error_{point_i}\le 1.5 \ m/s \\
5 \ \ \ \ \ 1.5 \ m/s < error_{point_i} \le 2.0 \ m/s \\
3 \ \ \ \ \ 2.0 \ m/s < error_{point_i} \le 2.5 \ m/s \\
1 \ \ \ \ \ 2.5 \ m/s < error_{point_i} \le 3.0 \ m/s \\
0 \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ error_{point_i} > 6.0 \ m/s \\
\end{aligned}
$$

<!-- 
1. The following metrics will be used to evaluate the SLAM algorithms' performance:

For a known ground truth trajectory ME000_gt.txt and an estimated trajectory ME000_est.txt, we calculate the translation and rotation error based on the normalized Relative Pose Error similar to the KITTI dataset. Different from KITTI, we compute translational and rotational errors for all possible subsequences of length (5, 10, 15, ...,40) meters.  The translational error and rotational error are then combined to the final score:  , where we use  to balance the two errors, because the average rotation speed (in degree) is 7 times bigger than the average translation speed on our dataset. 

Due to the scale ambiguity of the monocular image, a global scale factor is calculated before the error computation. 

2. Download the evaluation tools. (TODO)

    Download the tartanair_tools repository, and follow the instruction here.  -->


## Submit the results. 

### Prepare the trajectory
For each of the 12 trajectories of **LiDAR-inertial track**, you need to compute the **poses in IMU coordinate frame**, and save them in the estimated trajectory text file with the name sequnce_name.txt. Put all 12 files into a zip file with the following structure: 

```
    lidar_inertial_track.zip
    ├── SubT_MRS_Final_Challenge_UGV1.txt         # result file for the trajectory Final_Challenge_UGV1
    ├── SubT_MRS_Final_Challenge_UGV2.txt         # result file for the trajectory Final_Challenge_UGV2
    ├── SubT_MRS_Final_Challenge_UGV3.txt         # result file for the Final_Challenge_UGV3
    ├── SubT_MRS_Urban_Challenge_UGV1.txt         # result file for the Urban_Challenge_UGV1
    ├── SubT_MRS_Urban_Challenge_UGV2.txt         # result file for the Urban_Challenge_UGV2 
    ├── SubT_MRS_Laurel_Caverns_Handheld3.txt     # result file for the Laureal Cavern  
    ├── TartanAir_lidar_factory.txt               # result file for the trajectory lidar_factory 
    ├── TartanAir_lidar_ocean.txt                 # result file for the trajectory lidar_ocean 
    ├── TartanAir_lidar_sewerage.txt              # result file for the trajectory lidar_sewerage 
    │   (Below are Bonuses)
    ├── SubT_MRS_Hawkins_Long_Corridor_RC.txt     # result file for the trajectory Long Corridor 
    ├── SubT_MRS_Hawkins_Multi_Floor_LegRobot.txt # result file for the trajectory Multi Floor 
    └── SubT_MRS_MILL19_Block_LiDAR.txt           # result file for the trajectory Block LiDAR  


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
The estimated_trajecotry.txt file should have the following format: 


```

# timestamp_s tx ty tz qx qy qz qw
1.403636580013555527e+09 0.0 0.0 0.0 0.0 0.0 0.0 0.0

```

<br>
<br>
<br>
<br>
<br>

Here are some requirements for your estimated_trajectory.txt

- Each line in the text file contains a single pose.
- The format of each line is 'timestamp_s tx ty tz qx qy qz qw'. 
- tx ty tz (3 floats) give the position of IMU sensor to the world origin in the world frame.
- qx qy qz qw (4 floats) give the orientation of IMU in the form of a unit quaternion with respect to the world frame. 
- The trajectory can have an arbitrary initial position and orientation. However, we are using the IMU frame to define the motion. That is to say, the x-axis is pointing to forward, the y-axis is pointing left, the z-axis is pointing up.

### Submit in Gradescope  

- To submit the estimated trajectory into the submission system, you can follow the steps listed below:
    1. Register a account in the [GradeScope](http://gradescope.com/) and log into the website.
    2. Click the right-bottom `Add Course` button and enter the course-entry code: `K3EGGJ`, Then you can find the `iccv-lii` courses in your GradeScope homepage.
    3. Click the `iccv-lii` course and you will see the assignment named `Trajectory-result-submission` in the dashboard.
    4. Click the assignment and upload your `lidar_inertial_track.zip` file. Also please remember to input the group name as the leaderboard name. Then click the upload button.
        - You should directly compress the estimated result files of the trajectories into a zip file, not the folder containing the result files.
    5. After around 1 minutes, you will see the APE and RPE result of your trajectory in the leaderboard.

- Note: 
    1. You must submit all the 12 trajectories for lidar inertial track.
    2. The trajecotry should be complete. The duration of estimated trajecotry should be roughly same with ground truth trajectory. 

### Submit Report

Participants are requested to submit a report describing their methods along with the gradescope submission. A template for the same is provided here : <a href="Report/ICCV_Report_Template.zip" download> ICCV_Template_Report </a> . Please include your report pdf in the `lidar_inertial_track.zip` file.



## Challenge Rules 
1. Participants are welcome to form teams. A participant cannot be in multiple teams and a team must make submissions under a single account.  
2. Every day a team can submit for at most once on gradescope and the submission must be in a certain time window: 12:00 P.M. - 11:59 P.M. UTC. 
3. The size of every trajectory file submitted should be no more than 2 MB.
4. Every team <b>must submit a report</b> along with the gradescope submissions.  
5. Organizers reserve the right to make changes to the rules and timeline.  
6. Violation of the rules or other unfair activities may result in disqualification.  

##  🎉Lidar-inertial Leaderboard🎉

Leaderboard will be open on Gradescope when there is still enough time before the challenge ends.

## Contact us

If you have any question or see anything wrong, please do not hesitate to <b>post issues on this [github website](https://github.com/water-horse/ICCV2023_SLAM_Challenge.git)</b>. We would love to hear from your feedback! Every post will be responded with no spared effort within 36 hours.


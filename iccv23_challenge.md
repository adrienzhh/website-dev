---
title: SLAM Challenge
subtitle: ICCV 2023 Workshop of Robot Learning and SLAM
layout: page
show_sidebar: false
hide_footer: true
hero_height: is-medium
hero_image: /img/iccv/iccv2023_background.jpg
---

## Introduction

This document outlines the benchmarking procedure for evaluating Simultaneous Localization and Mapping (SLAM) algorithms. SLAM is a crucial component in robotics and computer vision systems, enabling real-time mapping of the environment while simultaneously estimating the robot's position within it. This benchmark aims to assess the performance of various SLAM algorithms under different conditions and datasets.

## Datasets

1. **Robot Exploration Dataset**
   - Description: This dataset consists of indoor environments, such as office buildings, corridors, and rooms, captured by various sensors like LiDAR, RGB-D cameras, or stereo cameras.
   - Challenges: Loop closures, dynamic objects, and varying lighting conditions may be present.

2. **TartanAir Dataset**
   This benchmark is based on the [TartanAir dataset](http://theairlab.org/tartanair-dataset/), which is collected in photo-realistic simulation environments based on the AirSim project. A special goal of this dataset is to focus on the challenging environments with changing light conditions, adverse weather, and dynamic objects. The four most important features of our dataset are:

   - **Large size diverse realistic data.** We collect the data in diverse environments with different styles, covering indoor/outdoor, different weather, different seasons, urban/rural.
   - **Multimodal ground truth labels.** We provide RGB stereo, depth, optical flow, and semantic segmentation images, which facilitates the training and evaluation of various visual SLAM methods. 
   - **Diversity of motion patterns.** The existing popular datasets such as KITTI and Cityscapes only cover very limited motion patterns, which are mostly moving straight forward plus small left or right turns. This regular motion is too simple to sufficiently test a visual SLAM algorithm. Our dataset covers much more diverse motion combinations in 3D space, which is significantly more difficult than existing datasets.
   - **Challenging Scenes.** We include challenging scenes with difficult lighting conditions, day-night alternating, low illumination, weather effects (rain, snow, wind and fog) and seasonal changes.
   Please refer to the TartanAir Dataset and the paper for more information. 

    ![GIF Figure 1](img/slam_challenge/abandonedfactory.gif) ![GIF Figure 2](img/slam_challenge/gascola.gif) \\
    ![GIF Figure 3](img/slam_challenge/hospital.gif) ![GIF Figure 4](img/slam_challenge/jananesealley.gif)

## Get Started

1. Download the testing data. 

   Click here to download the testing data for the monocular track. (Size: 7.65 GB)
   MD5 hash: 009b52e7d7b224ffb8a203db294ac9fb

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

2. Download the evaluation tools. 

    Download the tartanair_tools repository, and follow the instruction here. 

3. (Optional) Training data. 

    There are two ways to access the training data. 

    * Download data to your local machine

    * Access the data using Azure virtual machine

4. Submit the results. 

For each of the 16 trajectories (ME00X or MH00X) in the testing data, compute the camera poses, and save them in the text file with the name ME00X.txt or MH00X.txt. Put all 16 files into a zip file with the following structure: 

```
    FILENAME.zip
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

The camera pose file should have the same format as the ground truth file in the training data. It is a text file containing the translation and orientation of the camera in a fixed coordinate frame. Note that our automatic evaluation tool expects the estimated trajectory to be in this format. 

- Each line in the text file contains a single pose.
- The number of lines/poses must be the same as the number of image frames in that trajectory. 
- The format of each line is 'tx ty tz qx qy qz qw'. 
- tx ty tz (3 floats) give the position of the optical center of the color camera with respect to the world origin in the world frame.
- qx qy qz qw (4 floats) give the orientation of the optical center of the color camera in the form of a unit quaternion with respect to the world frame. 
- The trajectory can have an arbitrary initial position and orientation. However, we are using the NED frame to define the camera motion. That is to say, the x-axis is pointing to the camera's forward, the y-axis is pointing to the camera's right, the z-axis is pointing to the camera's downward.



## Metrics

The following metrics will be used to evaluate the SLAM algorithms' performance:

For a known ground truth trajectory ME000_gt.txt and an estimated trajectory ME000_est.txt, we calculate the translation and rotation error based on the normalized Relative Pose Error similar to the KITTI dataset. Different from KITTI, we compute translational and rotational errors for all possible subsequences of length (5, 10, 15, ...,40) meters.  The translational error and rotational error are then combined to the final score:  , where we use  to balance the two errors, because the average rotation speed (in degree) is 7 times bigger than the average translation speed on our dataset. 

Due to the scale ambiguity of the monocular image, a global scale factor is calculated before the error computation. 


# SLAM Benchmark Leaderboard

## Visual Benchmark

| Rank | Algorithm       | ATE (m)  | RPE (%)  | Loop Closure (%) | Map Completeness (%) | Map Accuracy (%) | Run-time (ms) | Memory (MB) |
|------|-----------------|----------|----------|------------------|---------------------|------------------|---------------|------------|
| 1    | Algorithm A     | 0.15     | 0.85     | 98.5             | 90.2                | 92.8             | 28.3          | 235.5      |
| 2    | Algorithm B     | 0.21     | 1.20     | 97.8             | 89.1                | 91.4             | 35.6          | 281.8      |
| 3    | Algorithm C     | 0.28     | 1.55     | 95.6             | 85.6                | 89.3             | 43.2          | 320.1      |
| 4    | Algorithm D     | 0.35     | 2.01     | 93.2             | 82.4                | 87.0             | 50.8          | 352.5      |
| 5    | Algorithm E     | 0.41     | 2.45     | 91.4             | 79.8                | 85.2             | 58.1          | 389.7      |

## LiDAR Benchmark

| Rank | Algorithm       | ATE (m)  | RPE (%)  | Loop Closure (%) | Map Completeness (%) | Map Accuracy (%) | Run-time (ms) | Memory (MB) |
|------|-----------------|----------|----------|------------------|---------------------|------------------|---------------|------------|
| 1    | Algorithm C     | 0.18     | 1.10     | 95.8             | 88.6                | 91.1             | 29.5          | 240.2      |
| 2    | Algorithm A     | 0.24     | 1.45     | 94.2             | 86.9                | 89.8             | 37.1          | 289.8      |
| 3    | Algorithm B     | 0.32     | 1.92     | 92.4             | 82.3                | 87.3             | 45.6          | 325.6      |
| 4    | Algorithm D     | 0.38     | 2.35     | 89.6             | 79.1                | 85.6             | 52.8          | 361.5      |
| 5    | Algorithm E     | 0.45     | 2.78     | 87.1             | 76.2                | 82.3             | 61.2          | 399.3      |

## Multi-modal Challenging Benchmark

| Rank | Algorithm       | ATE (m)  | RPE (%)  | Loop Closure (%) | Map Completeness (%) | Map Accuracy (%) | Run-time (ms) | Memory (MB) |
|------|-----------------|----------|----------|------------------|---------------------|------------------|---------------|------------|
| 1    | Algorithm A     | 0.12     | 0.75     | 99.2             | 91.3                | 93.5             | 23.1          | 225.5      |
| 2    | Algorithm C     | 0.19     | 1.10     | 97.6             | 88.7                | 91.2             | 31.8          | 275.8      |
| 3    | Algorithm B     | 0.26     | 1.60     | 96.1             | 86.4                | 89.1             | 40.5          | 318.3      |
| 4    | Algorithm D     | 0.33     | 2.05     | 93.8             | 83.2                | 87.6             | 48.9          | 358.9      |
| 5    | Algorithm E     | 0.39     | 2.50     | 91.5             | 80.6                | 85.3             | 57.3          | 395.5      |
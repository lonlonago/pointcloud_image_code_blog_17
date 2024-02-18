As shown in the picture: 

 ![avatar]( 20210531105759150.png) 

  An error occurs when using the pcl_sleep function. 

 Solution: 

 ① Find whether the header file #include < pcl/pcl_macros > ② Open the pcl_macros header file, find sleep, and modify it to Sleep; 

  The initial code in the header file: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957377688
  ```  
 Change to: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957377688
  ```  
  In fact, it is not the source code in PCL that is wrong. The above solution is simple and crude. 

 According to the blog post [C/C++] Sleep function usage: 

>  Sleep function

Function: Execute suspend for a period of time, that is, wait for a period of time to continue execution

Usage: Sleep (time)

Header file:

Under Windows -- > windows.hLinux -- > unistd.h

Attention:

Sleep is case sensitive, some compilers are uppercase, some are lowercase. The time in Sleep parentheses is in milliseconds under windows, while Linux is in seconds 

 Returning to the source code in PCL: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957377688
  ```  
 It can be seen that when the compilation environment is 32-bit, the uppercase Sleep is used, and milliseconds are passed in. In other environments, lowercase is used, and the time is passed in seconds. 

 The development environment I use is Win10 + VS2017 + Win64, which is treated as another development environment, so the correct change should be to add another judgment condition: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957377688
  ```  
 Or you can change the compilation environment to Win32. 



--------------------------------------------------------------------------------

 pcl_visualization library is built to quickly prototype the purpose and visualize the results of algorithms manipulating 3D point cloud data. A highgui routine similar to opencv displays 2D images, drawing basic 2D graphics on the screen, the library provides the following: 

 (1) Method of rendering and setting visual characteristics (such as color, size, transparency, etc.) in PCL arbitrary n-dimensional point cloud dataset pcl :: Poi n tC loud < T > format 

 ![avatar]( 976394-20170225162703507-224431255.jpg) 

 Methods for drawing basic 3D shapes on the screen (e.g., cylinders, spheres, lines, polygons, etc.), whether from point sets or parametric equations. 

 ![avatar]( 976394-20170225163254476-1117619011.jpg) 

 (3) Two-dimensional diagram of a histogram visualization module (pclhistogramvisualizer); 

 ![avatar]( 976394-20170225163411148-291383248.jpg) 

 (4) A large number of geometric and color processing PCL :: Point Cloud < T > datasets 

 ![avatar]( 976394-20170225163519710-713569465.jpg) 

 (5) a pcl :: R a nge Im a ge visualization module 

 ![avatar]( 976394-20170225163609163-124442403.jpg) 

                        . 

 1. class 

 The compilation result is as follows 

 ![avatar]( 976394-20170226133555804-680722212.png) 

 To be continued *************************8888888 



--------------------------------------------------------------------------------

#  Attention 

>  Viewer.addText ("does not support Chinese display", 20, 60, "text"); 

#  The simplest usage is to set only the position where the text is displayed: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573755705
  ```  
#  For a more complicated usage, you can set the font color and size: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573755705
  ```  
>   

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573755705
  ```  


--------------------------------------------------------------------------------

#  interaction problem 

 "PCL + QT" version interaction (updating) 

#  Configuration issues: 

 Summary of environment configuration issues for each version of "PCL + QT" (completed) 

#  The latest addition: "QT + PCL" supplement 

 "QT + PCL" supplement - add point cloud tree control (completed) 

 "QT + PCL" supplement - point cloud operation after adding tree controls (filtering, registration as an example (completed) 

 "QT + PCL" Supplement - Point Cloud Perspective Setup (Completed) 

#  First, the basic operation of "QT + PCL Chapter 1" 

 The reading display of point cloud in 1.1 qt (completed) 

 Point cloud file saving in 1.2 qt (completed) 

#  Second, "QT + PCL Chapter II" point cloud display 

 Software background settings in 2.1 qt (completed) 

 2.2 qt midpoint cloud rendering settings (completed) 

 Point cloud color setting in 2.3 qt (completed) 

 Adjust the point cloud size setting in 2.4 qt (completed) 

#  3. "QT + PCL Chapter 3" Point Cloud Filtering 

 Add voxel filtering to 3.1 qt (completed) 

 Add approximate voxels to 3.2 qt (completed) 

 Adding uniform sampling in 3.3 qt (completed) 

 Added fixed point sampling in 3.4 qt (completed) 

 Adding gridmin filtering to 3.5 qt (completed) 

 Add improved voxels to 3.6 qt 

 Adding statistical filtering to 3.7 qt (completed) 

 Added radius filtering in 3.8 qt (completed) 

 Adding Gaussian filtering to 3.9 qt (completed) 

 Add bilateral filtering in 3.10 qt 

 Add fast bilateral in 3.11 qt 

 Add projection filtering to 3.12 qt (completed) 

 Add median filtering in 3.13 qt 

 Add pass-through filtering to 3.14 qt (completed) 

 Add conditional filtering to 3.15 qt (completed) 

 Add morphological filtering to 3.16 qt 

 Add upsampling filter in 3.17 qt (completed) 

#  IV. Key Points of "QT + PCL Chapter IV" Point Cloud 

 Add the key point ISS in 4.1 qt (completed) 

 4.2 Added key point Harris to qt (completed) 

 Added key point SIFT in 4.3 qt (completed) 

#  Point cloud characteristics of "QT + PCL Chapter 5" 

 Adding point cloud normals to 5.1 qt 

 5.2 Qt to add feature PFH 

  5.3 qt add point cloud feature FPFH 

 Adding point cloud feature RSD in 5.4 qt 

 Adding point cloud feature 3DSC in 5.5 qt 

 Adding point cloud feature USC in 5.6 qt 

 5.7 Add point cloud feature SHOT in qt 

 5.8 qt add point cloud feature SPinImage 

 5.9 qt add point cloud feature RIFT 

 Adding point cloud feature NARF in 5.10 qt 

 5.11 qt add point cloud feature RopS 

 Adding point cloud feature VFH in 5.12 qt 

 Adding point cloud feature CVFH in 5.13 qt 

 5.14 Qt add point cloud feature OUR_CVFH 

 Adding point cloud feature ESF in 5.15 qt 

 Adding point cloud feature GFPFH in 5.16 qt 

 5.17 qt add point cloud feature GRSD 

#  "QT + PCL Chapter 6" Point Cloud Registration 

 Added icp registration series 1 to 6.1 qt (completed) 

 Added icp registration series 2 to 6.2 qt (completed) 

 Added icp registration series 3 to 6.3 qt (completed) 

 Added icp registration series four to 6.4 qt (completed) 

 6.5 QT Muscle Building ICP Registration Series 5 (Completed) 

 Added icp registration series six to 6.6 qt (completed) 

 Added 4pcs series to 6.7 qt with a 4pcs implementation (completed) 

 Added 4pcs series two k4pcs to 6.8 qt (completed) 

 Added 4pcs series three super4pcs implementation in 6.8 qt (completed) 

 Added feature registration series 1 in 6.9 qt 

 Added feature registration series 2 in 6.10 qt 

 Added feature registration series 3 in 6.11 qt 

 Added feature registration series 4 in 6.12 qt 

 Added feature registration series 5 in 6.13 qt 

 Added feature registration series 6 in 6.14 qt 

 Added point cloud registration NDT in 6.15 qt (completed) 

 6.16 Point Cloud Registration Advanced - GROR Registration (Completed) 

#  "QT + PCL Chapter 7" Point Cloud Segmentation 

 Added point cloud segmentation - straight line segmentation in 7.1 qt (completed) 

 7.2 Qt added point cloud segmentation - circular segmentation (completed) 

 Added point cloud segmentation-plane segmentation in 7.3 qt (completed) 

 Added point cloud segmentation-cylindrical segmentation in 7.4 qt (completed) 

 Added point cloud segmentation-Euclidean clustering in 7.5 qt (completed) 

 Adding point cloud segmentation in 7.6 qt - regional growth (completed) 

 Adding point cloud segmentation in 7.7 qt - area growth 2 

 Add point cloud segmentation-super voxel segmentation in 7.8 qt 

 7.9 qt to add point cloud segmentation - LCCP (completed) 

 Add point cloud segmentation-CPC in 7.10 qt (completed) 

 7.11 Qt added point cloud segmentation - minimum cut 

 Add point cloud segmentation in 7.12 qt - morphological segmentation 

 Add point cloud segmentation in 7.13 qt - progressive morphological segmentation 

#  8. "QT + PCL Chapter 8" Point Cloud Recognition 

 Add point cloud recognition in 8.1 qt 

#  "QT + PCL Chapter 9" Point Cloud Reconstruction 

 Added Point Cloud Reconstruction Series 1 in 9.1 qt - Greedy Triangulation (Completed) 

 Added Point Cloud Reconstruction Series 2-Poisson Reconstruction in 9.2 qt (completed) 

 Added point cloud reconstruction series 3-moving cube in 9.3 qt 



--------------------------------------------------------------------------------

Summary: 

 Utilizing line features to improve the localization accuracy of point-feature-based visual inertial SLAMs (VINS) is becoming increasingly important because they provide additional constraints on regularity in structured scenes. However, real-time performance has not been paid attention to. This paper introduces PL-VINS, a monocular VINS method with points and lines based on real-time optimization. It is developed on the basis of the latest point-based VINS Mono. It is observed that the current work is to use LSD algorithm to extract straight lines, but LSD is designed for the shape-structure representation of scenes, rather than for specific pose estimation problems. Due to its expensive cost, it becomes a bottleneck for real-time performance. This paper proposes an improved LSD algorithm through the study of implicit parameter adjustment and length suppression strategies. The improved LSD runs at least three times faster than LSD. Furthermore, by representing line landmarks with pucker coordinates, the line reprojection residuals are modeled as the midpoint-to-line distance, which is then minimized by iteratively updating the minimum four-parameter orthogonal representation of the pucker coordinates. Experiments on the public euro-benchmark dataset show that the positioning error of this method is 12-16% lower than that of the VINS-Mono algorithm at low power consumption CPU@1.1ghz at the same operating frequency. 

 ![avatar]( 20210106175911987.png) 

 Open Source Code: https://github.com/cnqiangfu/PL-VINS. Related Work and Major Contributions 

 This paper proposes PL-VINS, its features include: 

 (1) As far as I know, PL-VINS is the first monocular point and line VINS method based on real-time optimization (see table). 

 (2) For specific pose estimation problems, an improved LSD algorithm is proposed by studying implicit parameter adjustment and length suppression strategies, which is at least three times faster than the LSD algorithm. 

 (3) Point, line, and IMU information are effectively fused in an optimization-based sliding window to achieve high-precision attitude estimation. Line reprojection residuals are modeled as the midpoint-to-line distance, which is then minimized by iteratively updating the smallest four-parameter normal representation. 

 ![avatar]( 20210106180333321.png) 

 (4) Qualitative and quantitative experiments on the benchmark dataset EuRoc show that the method achieves higher performance than VINS Mono at the same operating frequency on a low-power CPU Intel Core i7-10710U@1.10GHz. This paper proposes a new scheme that extends the traditional SfM algorithm to make it suitable for stereo cameras and LiDAR sensors. This work is based on the simple idea that the long-range capabilities of LIDAR can be used to suppress relative motion between images. More specifically, we first implement a stereo vision SfM scheme that calculates the motion of the camera and estimates the three-dimensional position of the visual feature (structure). The LiDAR point cloud and visual features are then fused into a single optimization function, which is iteratively solved to optimize the camera's motion and structure. In our scheme, LiDAR data enhances the SfM algorithm in two ways: 

 1) LiDAR point cloud is used to detect and eliminate invalid image matching, making the stereo camera-based SfM scheme more robust to visual blur. 

 2) LiDAR point clouds are combined with visual features in a joint optimization framework to reduce motion drift. Our scheme enables more consistent and accurate motion estimation than state-of-the-art SfM algorithms. 

 The work of this paper mainly includes the following aspects: 

 1) The global SfM technology is applied to the stereo camera system to realize the motion initialization of the camera at the real scale. 

 2) LiDAR data is used to rule out invalid image matching, further enhancing the reliability of the scheme. 

 3) By combining the data from stereo cameras and lidar, we extend our previously proposed joint optimization scheme and improve the accuracy and consistency of the built model. 

 According to the different information fusion frameworks, the current VINS methods are divided into: 

 A, VINS method based on Kalman filter 

 The first tightly coupled Kalman filter (KF) -based VINS approach can be traced back to MSCKF, a multi-state constrained KF framework. Recently, Patrick et al. proposed OpenVINS, an open-source visual inertia estimation platform based on Extended Kalman (EKF). Both schemes use Shi Tomasi as a visual feature. Based on this platform, Yang et al. introduced line features or planar features or line and planar features to improve the performance of OpenVINS. 

 B. VINS method based on nonlinear optimization 

 In practice, nonlinear optimization-based methods are bundle adjustment (BA) -based methods, in which the pose is obtained by optimizing multiple constraints such as vision and IMU. This paper focuses on optimization-based VINS methods, which are divided into: 

 ** Point-based approach. ** The first method based on tightly coupled nonlinear optimization can be traced back to OKVIS, which is based on keyframes and BA implementations. On this basis, some optimization-based work is proposed. Among them, VINS Mono seems to be a monocular VINS benchmark because of its high robustness. Feature tracking uses Lucas-Kanade Tracker (KLT), and loop closure uses DBoW2. 4-DOF attitude map optimization and map merging. It has recently been extended to stereo vision and stereo + inertial navigation. It is worth noting that most of the current work uses ShiTomasi as a feature extraction tool and KLT as a feature tracker. These work may produce low-precision point feature extraction in challenging scenarios. In some cases, poor corner and IMU information is not sufficient to meet the requirements of high-precision positioning. 

 ![avatar]( 20210106180522843.png) 

 ** Point and line-based methods. ** It is increasingly important to utilize geometric information in point-based VINS systems, such as lines and planes. This paper focuses on line features from the perspective of real-time applications. How to introduce line features into point-based VINS methods is the key to ensure the effectiveness of this method. Most of the current work directly uses LSD in OpenCV for line extraction, but LSD is designed for structured environments rather than pose estimation problems, where a large number of lines can be regarded as outliers, which neither wastes computing resources nor easily generates outliers. In fact, for specific problems, we do not need to use lines to describe the scene in detail, but extract obvious line features. After detecting a straight line, these VINS methods employ LBD and KnnMatch algorithms for descriptive subcomputation and matching. Work on line matching Gomez-Ojeda et al. employed geometric constraints to match and weed out line outliers. Once the line correspondence is established, pose estimation can be performed. Under the BA-based optimization framework, the camera pose in the VINS method can be estimated by jointly minimizing the three residual terms of point, line, and IMU constraints. 

 Main content 

 ![avatar]( 20210106180617827.png) 

 Systematic overview, This paper proposes a monocular vision inertial navigation point-line SLAM method based on real-time optimization: PL-VINS. This method makes effective use of line features and improves the performance of existing VINS-Mono methods. This paper focuses on the process of line feature fusion. The general structure of pl-vins is shown in the figure. A, Preprocessing of observations 

 The PL-VINS system is started from this thread. Its function is to extract and align the raw information of both the camera and IMU measurements. For the input frame (RGB image) captured by the camera, point and line features are detected, tracked and optimized in parallel in the image. Here Shi-Tomasi is used to detect point features, KLT is used to track, and the best points and lines are preserved based on the geometric constraints of RANSAC. For line features, LSD in OpenCV is directly used for detection, and the LSD is modified to achieve real-time application. Line features are tracked based on LBD algorithm (descriptor) and KnnMatch (match). 

 For the raw gyroscope and accelerometer information for the IMU measurements, the work of VINS Mono is followed here to pre-integrate them between two successive frames. Initialization: The pre-processed measurement information is used to initialize the system, after which the values and inputs required to trigger the next thread are initialized. First, a graph structure consisting of high-scale camera pose and point, line landmarks is estimated in multiple frames. Next, the graph is aligned with the IMU pre-integration values, including velocity, gravity vector, and gyroscope deviation. Note that the external parameters between the IMU and the camera are pre-given. 

 B, local VIO 

 After initialization is complete, a tightly coupled optimization-based local visual inertial odometry (VIO) thread is turned on for high-precision six-degree-of-freedom camera pose estimation by minimizing all measurement residuals. First, three-dimensional (3D) point and line features are constructed by triangulating the point and line feature correspondence between the new frame and the old frame, and parameterized by inverse depth and Plcker coordinates, respectively. Second, a fixed-size sliding window is employed to find the optimal state vector, including pose, velocity, 3D features, acceleration, and gyroscope bias, by jointly minimizing the multi-residual function. While inputting new image frames, we marginalize the last frame in the sliding window to maintain the window size. Keyframes: Follow VINS Mono's keyframe selection criteria: the parallax between the current frame and the last keyframe is greater than a certain value or the number of tracked features is less than a certain value. 

 C, closing the loop 

 When the current frame is selected as the key frame, the closed loop thread is activated, its function is to search and decide whether the track forms a closed loop, and it can also be used for repositioning. 

 Line feature A, line feature detection 

 The current VINS method based on points and lines directly adopts LSD in OpenCV for line extraction. Due to its large amount of calculation, the time-consuming of 60~ 80ms per frame in the experiment has become a bottleneck for real-time applications. It is observed that LSD is designed for scene shape representation without parameter adjustment, rather than for a specific pose estimation problem. For detecting a large number of short-length line segments, but according to the pose estimation problem, they can be directly regarded as outliers. For a specific problem, we do not need to use lines to describe the scene finely, but detect obvious line segments. Interestingly, we further found that some hidden parameters in LSD can be adjusted to speed up the detection process. This paper modifies LSD based on the source code in OpenCV to speed up the extraction process from two aspects of hidden parameter adjustment. 

 ** 1, hidden parameter adjustment. ** Although LSD has no parameter adjustment, there are still some hidden parameters that can be optimized to speed up detection, which are explicitly made in this article. First, OpenCV uses the generated N-layer Gaussian pyramid to represent the original image, where the image is downsampled N-1 times and blurred N times, and then uses LSD to extract line segments in each layer image. We simplify the scale and layers of the pyramid, and experimentally, scale = 0.5, and N (layers) = 2 works well. Next, if the aligned area points in the closed rectangle are less than the threshold, then LSD sets the minimum density threshold to exclude line segments, where we set it to 0.6 to speed up the processing. Note that the extraction process is also time-consuming, but it is necessary to weed out unreliable line segments. To simplify the tuning process, all the values can be found in our open-source code. 

 ![avatar]( 20210106180751439.png) 

 ** 2, Exclude lines whose lengths do not match. ** Previous parameter adjustments help to simplify the detection process of the algorithm, we use length constraints to exclude some of these parameters. E.g. min (WI; HI) = 480, η = 0:125 means Lenmin = 60. Suitable for help extraction systems η = 125:0. Therefore, the modified LSD runs at least 3 times faster than the LSD. B, Line segment tracking and interior point retention 

 We adopt the popular line tracking strategy: LBD is used to calculate the descriptor of each line segment, and then KnnMatch is used to match. Then the initial line feature correspondence between frames is established. For possible line outliers, we use a linear refinement method based on geometric constraints to filter out the outliers. 

 C, line feature triangulation road punctuation 

 In the previous step, we established the (2D) line feature correspondence on the image plane. Now we estimate the corresponding 3D line marker by triangulating the correspondence. (This can be seen in the introduction of the specific paper) 

 D, line reprojection residual model 

 ![avatar]( 20210106180832748.png) 

 The linear reprojection residual model is the distance from the midpoint to the straight line, that is, the midpoint distance from the line segment to the projection line. The linear reprojection error in the image can be defined as: E. Sliding window optimization based on point, line and IMU 

 ![avatar]( 20210106180858995.png) 

 ![avatar]( 20210106180953368.png) 

 Optimize the state vector to obtain the maximum a posteriori estimate by minimizing the following objective functions: (See the paper for details) Comparison of experiments, where the positioning accuracy and real-time performance of PL-VINS on the public EuRoc dataset are evaluated. All experiments are performed on an Intel Core i7-10710U processor @1.10ghz. PL-VINS is implemented using ubuntu 18.04 with ROS-Melodic. A, Precision comparison, where the positioning accuracy of PL-VINS is tested, and the accuracy is evaluated by root mean square error (RMSE) of absolute trajectory error (ATE) and relative attitude error (RPE): Given PL-SLAM based on VINS-Mono, we first compare them in the most challenging sequence of the EuRoc dataset. The following table provides an ATE comparison, where bold indicates better results. From this table, we can draw conclusions: 

 1.PL-VINS has higher accuracy than the V1-02 dataset. 

 2. A closed loop (Loop) is a necessary step to eliminate cumulative errors and is applicable to all sequences. Taking VINS-Mono as an example, 0.375 is reduced to 0.220 in the MH-04-hard sequence. 

 3. Summarizing from the last line, PL-SLAM is the better approach because by making additional use of line characteristics, position errors are reduced by an average of 16% compared to VINS Mono. 

 ![avatar]( 20210106181038270.png) 

 ![avatar]( 20210106181052276.png) 

 ![avatar]( 20210106181128501.png) 

 The figure below provides a visual comparison regarding the trajectory of motion in 3D. Figure 5 provides an example of a visualization in MH-04, where, PL-VINS also reconstructs the line landmark map and restores motion by tracking it. B. Real-time analysis. The PL-VINS is compared with the optimization-based monocular VINS method. The real-time performance of PL-VINS is discussed. The table below provides a comparison of the average execution time of the three methods. Where threads 1, 2, and 3 represent measurement preprocessing, local VIO, and loop closure, respectively. In conclusion, this paper introduces PL-VINS, the first monocular point and line VINS based on real-time optimization. Among them, for a specific attitude estimation problem, an improved LSD algorithm is proposed to speed up the line detection process by studying the implicit parameter adjustment and line segment length suppression strategies. The improved LSD can be used in existing pose estimation methods based on line correspondence. In addition, using the line constraint in the sliding optimization window, high-precision attitude estimation is effectively realized through four-parameter orthogonal representation and midpoint-to-line distance measurement. Therefore, PL-VINS has higher positioning accuracy than the state-of-the-art VINSMono at the same operating rate. 



--------------------------------------------------------------------------------

#  I. Introduction 

 Let's take a random point cloud as an example. As shown in the figure, we need to do the following: 

 1) Extract the boundaries accurately 2) Sort the space points and send them to the robot clockwise or counterclockwise   

#  II. Idea 1: Using Reconstruction Ideas 

 1. Principle 

 ![avatar]( c351f7958d054556ad63c07623938302.png) 

 1) Reconstruction effect: As shown in the figure, although the triangular reconstruction is performed, the reconstruction algorithm still reconstructs the error, mistaking the boundary point as an internal point. At this time, reconstruction optimization is required. 

 ![avatar]( 2e9c9421e8ac413cb12043bb80018b2f.png) 

  2) Optimization strategy: According to the reconstructed mesh, we can draw that the wrong triangular surface and the correct triangular surface are often geometrically different, such as boundaries, surface area, etc.; accordingly, we design a geometric feature filter to filter out the differentiated surface. The filter is selected according to its own point cloud characteristics. Finally, after adding the geometric feature filter to the reconstruction result, it can be seen that the effect is very superior. 3) Boundary extraction: According to the above principle, the boundary extraction is carried out. The effect is as follows: 4) Sequential extraction: After we extract the boundary points through reconstruction, we can also sort the spatial points according to the half-edge data structure. The specific principle will not be described in detail. The final effect diagram is shown in 3. 3. Realize the effect 

 ![avatar]( 9dbcff0b32ea4058be9df3695b8a4c75.gif) 

#  3. Idea 2: Using PCL boundary extraction method + 3D space point sorting 

 1. Principle 

 2. Implementation steps 

 ![avatar]( 7b7e7b7e9b874955b7e954313e08227e.png) 

 1) Boundary extraction: Several boundary extraction methods commonly found in PCL are used, and the results are as follows: 1) Based on normal: parameters (30, 30, 2) - just record it in case of subsequent needs.  

 ![avatar]( 0f3ccad3514e4676b8ca151b5976cdad.png) 

 2) Rolling ball method: The effect is not good, and the parameters may not work. Try the relevant algorithm in cgal later.  

 2) Cluster segmentation: The corresponding inner and outer boundaries can be segmented by clustering segmentation. 

 ![avatar]( a1ecff368faa4e57bd0825460bb6de18.png) 

 3) Spatial point sorting: refer to the two-dimensional boundary point cloud sequence (reverse) sorting, point cloud man - two-dimensional boundary point sorting. The result is shown in 3. This method will have misjudgments where local changes are obvious, which still needs attention. 

 3. Achieve results 

 ![avatar]( 2dc2a222adab43a880d8c97e404742c8.gif) 

 ![avatar]( bfe5e1238a7443eabba09694c2e09e06.gif) 

 ![avatar]( d59d8a8bcfd1412888d8a37b23843fc5.gif) 

 ![avatar]( 78d38f4ac19f4e0a9b596448b2fb32ee.gif) 

 Inner boundary, outer boundary, other data   

#  IV. Follow-up 

 In the future, the position information needs to be sent to the robot to guide the robot's trajectory optimization. However, the current boundary point is not a uniform point, and homogeneous sampling is still required. This step is not mentioned for the time being. 

 The code will be added to "Point Cloud Algorithm Processing" later, over!!!! 

 ![avatar]( fc1a4cb871084677be723754f99cde3f.jpeg) 



--------------------------------------------------------------------------------

![avatar]( 9fcefd197ff742439c0a8453333fbf73.png) 

 Implementation of DBSCAN Clustering Algorithm Based on PCL 

 DBSCAN.hpp file 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573741368
  ```  
 How to use 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573741368
  ```  


--------------------------------------------------------------------------------

![avatar]( 4f85c07ed02d4cf0b1c25dd1fd9c7a14.png) 

 The Use of DBSCAN Algorithm on Point Cloud 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573734549
  ```  


--------------------------------------------------------------------------------

 ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573711322
  ```  


--------------------------------------------------------------------------------

##  Point cloud filtering operation summary 

#  1. Summary 

 Point cloud filtering is divided into many types according to different usages. Common filters include voxel, pass-through, statistics, projection, random downsampling, uniform downsampling, conditional filtering, spatial plane segmentation, progressive voxel, Gaussian filtering, bilateral filtering, etc. 

#  2. Specific methods 

 Initialization: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
##  2.1 Voxel filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607204252334.png) 

 The results are as follows:   

##  2.2 Pass-through filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607205541722.png) 

 It can be seen that the 40mm-50mm direct z-axis is filtered out.   

##  2.3 Statistical filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607210930740.png) 

 Statistical filter sampling is performed on point cloud data with less than 50 points around.  

 ![avatar]( 20210607210917569.png) 

##  2.4 Projection filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607211436369.png) 

 Projected onto the plane where x + 2y + 3z = 4 = 0.  

##  2.5 Random downsampling 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607211939310.png) 

 Random downsampling to 5000 points  

 ![avatar]( 20210607211918966.png) 

##  2.6 Uniform downsampling 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607212338574.png) 

 ![avatar]( 20210607212358540.png) 

 The reduced sampling radius leafsize is set to 1.   

##  2.7 Conditional filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607212921651.png) 

 As an extension of pass-through filtering, conditional filtering can be said to be the simplest conditional filtering.  

 ![avatar]( 20210607212844327.png) 

##  2.8 Spatial plane segmentation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607213635837.png) 

 Spatial plane segmentation is a three-dimensional space with a plane as the interface, and z = 50 is the interface in the figure.  

 ![avatar]( 20210607213621696.png) 

##  2.9 Progressive Voxels 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 2021060721434743.png) 

 The principle of progressive voxels is similar to that of voxels, both of which mesh the space, except that the points selected to replace the grid are inconsistent. Progressive voxels handle details slightly worse and are faster.  

 ![avatar]( 20210607214220808.png) 

##  2.10 Gaussian Filtering 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 ![avatar]( 20210607214753753.png) 

 Gaussian filter is used for smoothing in two-dimensional images, and the effect is the same in three-dimensional point clouds. As shown in the figure. It works better for point clouds with obvious noise.  

#  3. Summary 

 In addition to the common point cloud filtering methods mentioned above, there are many filtering methods that are not described in detail, such as radius filtering, bilateral filtering, etc. The basic point cloud filtering will be updated completely when the time comes. 

 Visual code, point cloud visual updates are available. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573765867
  ```  
 Let's learn together and make progress together! 



--------------------------------------------------------------------------------

#  Demo 

 ![avatar]( aa83ae62a3d942a0835676f1423e1115.gif) 

 Official datasets, own data  

#  Project address 

 GitHub link: Go-icp 

#  Reproduction process 

 ![avatar]( 3f126c2fce96459cb1d1178232b9b5ff.png) 

 1. Download the source code, decompress it after the download is completed, and copy all the .h and .cpp files in the folder to the new project without any dependencies. 2. Create a new vs project, add the copied files to the corresponding header files and source files. At this time, you can directly compile and run. According to the jly_main function, set the corresponding debugging parameters, as shown in the figure below, the first and second are the point cloud data to be matched, txt format, the third is the point after random sampling, if not set, the default is all point calculation, set to 500 points, the fourth item is the config file, the initial parameters required for registration, and the fifth item is the output file. Write the registered rotation matrix and translation matrix to the file. 3. Refer to the note in github, build3d distance time is about 20-25s, so most of our time is wasted on build 3d distance. 4. According to github, as shown in the figure below, the input format of the point cloud is txt format. First, the number of point clouds is not friendly to our common pcd format, and the display effect is particularly inconvenient. Therefore, we change the read operation in the source code and read the pcd file. 

 ![avatar]( 6370654163334020b535bdcca6f01c04.png) 

 First add pcl_release property list, as shown in the following figure: 

 ![avatar]( 6e0aae1144034fd186cc002dee6e5428.png) 

  Change the point cloud of reading the file in jly_main .cpp as follows: The original read file: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957376596
  ```  
 After the change: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957376596
  ```  
#  dataset testing 

 ![avatar]( 08f58baa1caf4b179ba9e2d8d98ea1b1.png) 

 ![avatar]( 27a6f10d92d940b5818e4fb7f2e2b85f.png) 

 Green is the data_bunny after matching, as shown in the figure, the matching effect is still very good. For the rest of the dataset  

#  follow-up 

 I haven't read the relevant papers carefully, I haven't studied the parameters, I just went through it whole-heartedly, and I feel that the real-time performance of this algorithm is not very good. The subsequent related operations will also be integrated into QT + PCL, learn together, and progress together. 



--------------------------------------------------------------------------------

#  Demo 

 ![avatar]( e6fa0ae5c2b44ca5bd45d79400d336c3.gif) 

#  Project address 

 GitHub link: FastGlobalRegistration paper address: FastGlobalRegistration paper 

#  Second, the reproduction process 

 ![avatar]( 69019bf244d9473aa3a68f1222f7e47f.png) 

 1. Download the source code, as shown in the figure below  

 ![avatar]( 3e51b8cc375b473bb4d478c45a89b1e0.png) 

 2. Find the .cpp and .h files in the following folders, in the FastGlobalRegistration /sources/FastGlobalRegistration folder. And copy it to the new project. 3. Vs new project, add the above code to the project, and add the pcl-related attributes to the project. As shown in the figure below, evaluation is evaluation-related code, which can not be added. Adding pcl attributes does not require adding additional eigen libraries and flann libraries. It comes with pcl, which is also convenient for subsequent changes later.  

 ![avatar]( 54868c2bc245401491f181a882f839d3.png) 

 4. Code test, according to the relevant code in the main function, set the relevant parameters, where argv [1] and argv [2] represent the feature .bin file after calculating the ten thousand feature descriptors, and argv [3] is set to the output txt format file. As follows: 5. Effect display; original two point clouds: After registration: It can be seen that the registration effect is very good, and according to the paper, the registration time is also very fast. 

#  III. Data set testing 

 ![avatar]( e8fcb73160354775859de041feb88fdb.png) 

 ![avatar]( 932fb82453e947a9b4aed43222aed02e.png) 

 1. Since what needs to be input in the project is the calculated FPFH file, the FPFH file needs to be calculated first, and then saved. During the read operation, this process is very time-consuming. So we need to change the original code, use PCL to calculate and register in real time. Just save the FPFH and read and run it directly after the read operation is replaced by the FPFH feature descriptor. Replace the code in Figure 1 with Figure 2.   

 The change code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573727212
  ```  
 ![avatar]( 55c0cbe8eb6b42e88d50abf8fef21a68.png) 

 ![avatar]( ce0661a6a03e47e09b68f2c464d9a092.png) 

 2. The registration effect, the blue is the point cloud after registration, the effect is still relatively good.   

#  follow-up 

 Subsequent related demos will also be integrated into QT + PCL. 

 Open3D + python related code: python implementation of fast global registration 



--------------------------------------------------------------------------------

#  code implementation 

 Super4pcs + qt has been implemented 

#  Demo 

 ![avatar]( 47ee1529def84eb29ccc94de339ba09b.gif) 

#  Project address 

 GitHub: Project link, documentation: super4pcs 

#  Reproduction process 

 Since the original github of Super4pcs is no longer maintained, the new one is transferred to opengr, which is the link above. Therefore, to implement super4pcs, the following operations are required. 

##  1. Download the source code 

 ![avatar]( 8aacfad8474f4d0292f288955876e6eb.png) 

 ![avatar]( 564d52d01d0e492fadca4c22a76757bd.png) 

 After unzipping, the following folders are obtained, but in the 3rdparty file, the happly folder and the stb folder are empty, so they need to be downloaded separately. Open the project address, click on the relevant links respectively, and you can download the corresponding folder. Download and unzip it, and put it in the corresponding folder. The complete result is as follows:    

##  2、cmake 

 ![avatar]( a9464c4e890345df877e72bb1bfdc9bc.png) 

 Precautions, before using VS2015, the operation failed, using VS2019, cmake was successful once, and new build and install folders were created under the folder  

 ![avatar]( 0f92acc7adfa4efba3af648c68e050ec.png) 

 ![avatar]( 1abd538c515a42d0853ca031918397df.png) 

 ![avatar]( df2e6236b6904d219e25ae041fad648d.png) 

 ![avatar]( af83b7aa4d7f4e4298ee66b8a94620a6.png) 

 ![avatar]( e552b2e3a30a4ae0934c0c2d0cd66951.png) 

 The cmake process is as follows: click configure, wait, and the following red part will appear    

 Click Advanced, change the place in the picture above, 1), Eigen3 is changed to the Eigen library that comes with pcl, that is, the same path as Eigen above. 2), Cancel ADvanced, and change the path in the picture to the new install folder started in this article. Click generate to complete cmake. 

##  3. Run the sln file in the build folder to generate header files and lib files 

 ![avatar]( 662dcc73953d4654a1fdaddbca676a44.png) 

 ![avatar]( d2f89608362a42c18fd3af80a67bb2e6.png) 

  Select Build in Release 64 mode, all_build first, then install.  

 ![avatar]( c3fe2eecf35041be8ba4b66c22ead507.png) 

 After completion, under the install folder, the following files will come out. At this time, the include lib file of super4pcs we want is already available. Later, we only need to configure the following to run.  

##  4. Configuration file 

 ![avatar]( 5c8c7533696e41dcb79d711892f871f7.png) 

 ![avatar]( 92fcb643939a41fd9413cba4c75b1e12.png) 

 ![avatar]( 0df75326a4234eedb596e7c70702e7a5.png) 

 New vs project, first add the configured PCL attribute table, and then create a new super_4pcs related attribute table. super_4pcs attribute table is set as follows, the standard three processes, do not add there is no problem I do not know, I added.   

##  5. Test run 

 Add header file 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573758843
  ```  
 The registration code is basically the same as the pcl module 4pcs module, you can refer to the previous 4pcs code 4pcs test. 

#  dataset testing 

 ![avatar]( 4c2a1b0fedf946709764dc044f315b22.png) 

  The algorithm is more friendly to low overlap rate. I tried an overlap rate of only about 0.2, and it was well coarse. 

#  follow-up 

 Subsequent code will also be integrated into QT + PCL to learn and progress together. 



--------------------------------------------------------------------------------

In point cloud registration, sometimes the number of point clouds is too large, and key point extraction is required. Here are several key point extraction algorithms for point cloud PCL. 

 First, iss key points The specific principle of extracting iss key points can be viewed in related papers. The following main parameter settings are as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573726312
  ```  
 The experimental results are as follows: 

 ![avatar]( 20190410143302665.png) 

 Second, sift key point extraction, because the sift key point needs to return strength information, so set it at the beginning: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573726312
  ```  
 The main parameters are set as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573726312
  ```  
 ![avatar]( 20190410143645802.png) 

 The result is as follows  

 ![avatar]( 20190410143658365.png) 



--------------------------------------------------------------------------------

![avatar]( 36869d58357242559885764c2f304c69.png) 

  First, the implementation code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573759608
  ```  
##  Second, the test data 

 https://download.csdn.net/download/u014311125/86754445 



--------------------------------------------------------------------------------

#  Demo 

 ![avatar]( 221874d2ea504810ac394aacf1df4ffa.gif) 

#  Project address 

 github：3d-line_detection 

 Paper address: 

#  Reproduction process 

 ![avatar]( 604d58f151d34c4ba2f9f7e7c1d68e91.png) 

 1. Download the source code, open the src folder, and copy the .h and .cpp files in the file to the new vs project. 3. VS test 

 ![avatar]( 16ff1e1006964d76a7622c8dc7e4325b.png) 

 Create a new VS project and add the copied file to the project, as shown in the following figure: Configuration properties: The author's github writes that only opencv and openmp dependencies are required, so configure the opencv property and add it to the project. Generate it, there may be an error at this time, mainly because the opencv version is inconsistent, which will cause the data in the department cv to have an undefined identifier. At this time, the opencv header file needs to be added. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573794956
  ```  
 It shows that the compilation is successful, and then the point cloud data can be tested. The main function is as follows, where argv [1] represents the input txt file, and argv [2] represents the output two files 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573794956
  ```  
 If you want to save it for real-time display in pcd format, you only need to save the last two files txt as pcd. Taking writeOutLines as an example, the code is changed to the following to save it as a pcd format file. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573794956
  ```  
#  dataset testing 

 ![avatar]( bfcf0bd09a4e494a90a1f7374bbfe643.png) 

 ![avatar]( 8327db8a767949bdb8fbf1bc3d0533b3.png) 

 For cartons   

 ![avatar]( de225bed93454763816562326d4249f2.png) 

 Other data, from the effect, the results are still excellent.  

#  follow-up 

 Subsequent algorithms will be integrated into QT + PCL to learn and progress together. 



--------------------------------------------------------------------------------

![avatar]( fa93c9d360c7400b80cd7763332120ba.gif) 

 In addition to indicators, the comparison between multiple models also needs to be able to visually compare the visualization results. This time, I will introduce how to use open3d to open two windows at the same time to load the results of the two models, and at the same time realize the linkage of the two windows, that is, when one window is dragged or scaled, the other window also does the same transformation. Point cloud visualization: using open3d to realize point cloud continuous playback. This article introduces how to continuously play point cloud data. It introduces three methods. I gave the code implementation of the two methods in that article. Today, I use the second method to realize the linkage of two windows and can continuously play data, that is, the multi-threaded method. 

##  Multi-window linkage 

 When using open3d visualization, multiple windows can be loaded at the same time. Each Visualizer can create one window. The following code is to load two windows at the same time 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Open3D does not directly provide a way to link two windows, but we can assign the camera pose parameter of the first window to the second window, so that when we operate the first window (zoom, drag, rotate), the data in the other window can be changed directly. The core code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Where CTR is a visual control used to obtain and set camera parameters. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
##  Second, multi-threaded settings 

 Point cloud visualization: using open3d to achieve point cloud continuous playback introduced in open3d provides a callback function method for continuous playback of data and keyboard events, but here we cannot use the callback function to load two windows at the same time, so we must achieve continuous playback of data by ourselves. My strategy is as follows: use a sub-thread to load data, and use a sub-thread to monitor keyboard events. The main thread is used for visualization and constantly flashes the window. When the read data changes, the results displayed by the window are changed. 

###  2.1. Loading data 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Here I use two loops, the outermost layer is always true, in order to realize that the data can be played back to the end, the second data is loaded, and there is a play_status variable, which is prepared for keyboard events, used to realize the space bar to pause or play data. Please note that I only load one kind of data here, the two windows visualize the same set of data, the point cloud should be one set of data when actually used, and the box predicted by the model should be two sets. 

###  2.2. Keyboard events 

 The python library I use here is the keyboard of pynput, which mainly implements pause play (space bar), back (left arrow), and forward (right arrow). Pause and play are relatively simple, that is, when receiving the operation of pressing the space bar, change the state of the variable play_status. If the data is in the playing state (PlayStatus.start), change it to the suspended state (PlayStatus.stop), and vice versa. The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 The logic used for forward and backward is the same. Here is an example for forward. First, if it is in the playing state, you need to pause the playback first, and then increase the data id to be loaded by one to read the point cloud and box. Note that the loaded point cloud and box are global variables. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
###  2.3. Open3D loads two windows simultaneously 

 Just create two Visualizers. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Both windows load the same point cloud object. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Keep refreshing the window, assigning the camera parameters of the first window to the second window 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
##  III. Code and test data 

 Link: https://pan.baidu.com/s/1yuSbk7gqBdYdJsK9xSjkNQ Extraction Code: w1yw 



--------------------------------------------------------------------------------

#  First, the effect display 

 ![avatar]( c93db7a7792f41259cced418d86aeece.gif) 

#  Second, VS operation 

 Recently, after communicating with his friends, he found a useful registration method and put it here to implement it 

##  2.1 github source code download 

 gror 

##  2.2 Compile and run 

 ![avatar]( 1a4fe62864734453b734c3b47f9d8e6c.png) 

 The downloaded source code is added to vs, and pcl environment variables are added to compile and run. It also works well for point clouds with relatively low overlap rates  

 The overlap rate between the red target point cloud and the original point cloud is 50%, and the registration effect is good 

 ![avatar]( 0a27cdcdb9054610bb512fc606d3ffa6.png) 

#  III. Follow-up integration 

 It will be integrated into the column "PCL + QT" later. 



--------------------------------------------------------------------------------

#  I. Basic information 

 ![avatar]( 14151f7341b245088cb40e1559aace36.png) 

 Data download address: Stanford3dDataset_v1, the downloaded compressed package has 4.79G. After decompression, there are 6 folders, each folder represents a region  

 ![avatar]( 72532c9fe5b04887812b5016b85b35e3.png) 

 Each area folder is divided into subfolders for each room.  

 ![avatar]( 36d5856d90224b66befec29dc144cbe9.png) 

 Under each room folder is a point cloud file stored in txt format and Annotations, the label folder for that room.  

 ![avatar]( 3e31a9a79af0456aa0b13d34ad982ace.png) 

 The effect of opening the txt file in cloudcompare software  

 The Annotations folder contains the point cloud files for each component stored separately in this room, so the file name is the label for this part. 

 ![avatar]( 36328ff114d54d88886925dd29ecdca1.png) 

#  II. Data preprocessing 

##  2.1. Data cleaning 

 There are some errors in the directly decompressed data, mainly because a line of some files has a few more characters, such as Area_5\ office_19\ Annotations\ ceiling_1. Txt has a line of data containing characters, resulting in data operation failure. 

 ![avatar]( d62462dc9e19452eb5d9b0b1e76b8b05.png) 

##  2.2. Label visualization 

 The first section introduces that the label of S3DIS is actually the file name of the file of each component of the room. Here we merge the various components and then convert the file name to the label column. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 Where anno_paths txt is the following content 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 class_names is the following 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 Save it as txt and put it in the meta folder. 

 The effect is as follows: a single room 

 ![avatar]( 4692f6a0b21b451eb5d10318c39a9cb0.png) 

  Area1  Area_2  

 ![avatar]( 9e18d577301846a1b56a6a3c962198f0.png) 

 Area_3  

 ![avatar]( 8da0cd8fa4384f2eb3e2d01f6ded5237.png) 

 Area_4  

 ![avatar]( cbca8c898e3c401d80c98e8c34fdf6ad.png) 

 Area_5  

 ![avatar]( a300ef564fb84cdca7c363f0e399c064.png) 

 Area_6  



--------------------------------------------------------------------------------

#  I. Basic information 

 Semantic3D dataset and provides a large labeled 3D point cloud dataset of natural scenes with over 4 billion total points. It also covers a range of different urban scenes: churches, streets, railway tracks, squares, villages, football fields, castles and much more. The point cloud provided by the dataset uses state-of-the-art equipment for static scanning and contains very fine detail. Designed to help data-demanding methods such as deep neural networks make the most of their capabilities and learn richer 3D representations than ever before. 

 论文:SEMANTIC3D.NET: A NEW LARGE-SCALE POINT CLOUD CLASSIFICATION BENCHMARK 

 Data download address: semantic-8, reduce-8 

#  Ii. data analytics 

 There are two datasets given by Semantic 3D's official website, semantic-8 and reduce-8. The training dataset part of these two datasets is the same, including point cloud data in 15 urban or rural areas; the difference is in the test set part, Semantic-8's test set is also a complete point cloud dataset in 15 areas, and reduce-8 is considering that some neural networks have higher requirements for computing. Point cloud data in 4 areas are selected in the 15 test sets of Semantic-8, and then downsampled by 0.01m. 

##  2.1 The training dataset 

 The training dataset includes point cloud data for 15 regions (urban, rural) with a total of more than 1 billion points. 

 The categories are divided as follows: 

 Points labeled 0 are invalid and do not participate in training. 

 ![avatar]( b4b7cbd6ec7548ff8b0b9e7b2c8ceb5f.png) 

 ![avatar]( 91dba4ec778e4bf0ae580e86b903e65c.png) 

 ![avatar]( 966e7ec86a0647e8a1c6fe41abcac572.png) 

##  2.2 Semantic-8 test set 

 Semantic-8 test set also includes point cloud data for 15 regions 

 ![avatar]( 7273f52e8c404933aaaf96877389a2f5.png) 

 ![avatar]( 4bf739bdb89b4dbaa0f8d8a5f6985e2b.png) 

 ![avatar]( 5ab8aab777dc432c9cab47251faf5b84.png) 

##  2.3. Reduce-8 test set 

 The test set of Reduce-8 is to select 4 point cloud data in the test set of Semantic-8, and then do 0.01m downsampling processing. 

 ![avatar]( 213fc03383f84423b30528a26499a07e.png) 

 ![avatar]( 7049b8bfdfa249bb9b7b81c705b1db3c.png) 

#  III. Data processing 

 Note that the 0 in the label of the training data provided by Semantic3D represents an invalid value, because it is best to remove the 0-labeled points when visualizing. 

##  3.1. Splicing coordinates and labels 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573782036
  ```  
 Remove the visualization of label 0 

 ![avatar]( 627815aab97647df90d6f488eb9ab72b.png) 

 Visualization without removing label 0 

 ![avatar]( 98c969081fde48098f52208d1c34448f.png) 

##  3.2, test set evaluation index acquisition method 

 After training the point cloud semantic segmentation network using the Semantic3D dataset, only the corresponding label file will be generated during the test. At the same time, in order to get the evaluation results of the test set, the generated label file needs to be uploaded to the Semantic3D official website for index calculation. 

 3.2.1, account registration, login 

 ![avatar]( 4c959bca893748689f5b900069865e36.png) 

 3.2.2, create a classifier 

 ![avatar]( 61809050cac94f75ab51f921aad7da41.png) 

 ![avatar]( 211891828a1f4e019b29610a311a360d.png) 

 ![avatar]( 42aaacc1388d4eb3ba0db1a28ac56873.png) 

 3.2.3, submit the test results, pay attention to save the zip format submission 

 ![avatar]( e5dcb63e190d4c64a728f4db9e0af9e9.png) 

 ![avatar]( c1759c79e6e6439c8813aef158fc055f.png) 

 3.2.4, view the evaluation indicators 

 ![avatar]( 01d2fd02d3474f0fa9edcad57eeae68b.png) 

 ![avatar]( 4244f2a138494edea7146bd59c11c6ee.png) 

##  3.3 Visualization of validation set results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573782036
  ```  
 View results in point_cloud 

 ![avatar]( 6cb4bed001de4c6b9d60ef2577c2d3b4.png) 

 ![avatar]( 89586dacd8984b3b905d3301fa7ca5a7.png) 



--------------------------------------------------------------------------------


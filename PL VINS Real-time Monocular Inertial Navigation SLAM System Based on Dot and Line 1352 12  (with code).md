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


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


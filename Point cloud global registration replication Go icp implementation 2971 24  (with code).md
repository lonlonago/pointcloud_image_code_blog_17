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


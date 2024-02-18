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


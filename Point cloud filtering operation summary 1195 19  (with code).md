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


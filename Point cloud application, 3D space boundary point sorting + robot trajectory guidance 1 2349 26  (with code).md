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


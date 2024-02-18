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


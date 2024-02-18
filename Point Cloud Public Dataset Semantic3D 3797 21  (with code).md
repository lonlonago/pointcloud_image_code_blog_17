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


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


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


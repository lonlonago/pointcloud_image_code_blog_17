![avatar]( fa93c9d360c7400b80cd7763332120ba.gif) 

 In addition to indicators, the comparison between multiple models also needs to be able to visually compare the visualization results. This time, I will introduce how to use open3d to open two windows at the same time to load the results of the two models, and at the same time realize the linkage of the two windows, that is, when one window is dragged or scaled, the other window also does the same transformation. Point cloud visualization: using open3d to realize point cloud continuous playback. This article introduces how to continuously play point cloud data. It introduces three methods. I gave the code implementation of the two methods in that article. Today, I use the second method to realize the linkage of two windows and can continuously play data, that is, the multi-threaded method. 

##  Multi-window linkage 

 When using open3d visualization, multiple windows can be loaded at the same time. Each Visualizer can create one window. The following code is to load two windows at the same time 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Open3D does not directly provide a way to link two windows, but we can assign the camera pose parameter of the first window to the second window, so that when we operate the first window (zoom, drag, rotate), the data in the other window can be changed directly. The core code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Where CTR is a visual control used to obtain and set camera parameters. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
##  Second, multi-threaded settings 

 Point cloud visualization: using open3d to achieve point cloud continuous playback introduced in open3d provides a callback function method for continuous playback of data and keyboard events, but here we cannot use the callback function to load two windows at the same time, so we must achieve continuous playback of data by ourselves. My strategy is as follows: use a sub-thread to load data, and use a sub-thread to monitor keyboard events. The main thread is used for visualization and constantly flashes the window. When the read data changes, the results displayed by the window are changed. 

###  2.1. Loading data 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Here I use two loops, the outermost layer is always true, in order to realize that the data can be played back to the end, the second data is loaded, and there is a play_status variable, which is prepared for keyboard events, used to realize the space bar to pause or play data. Please note that I only load one kind of data here, the two windows visualize the same set of data, the point cloud should be one set of data when actually used, and the box predicted by the model should be two sets. 

###  2.2. Keyboard events 

 The python library I use here is the keyboard of pynput, which mainly implements pause play (space bar), back (left arrow), and forward (right arrow). Pause and play are relatively simple, that is, when receiving the operation of pressing the space bar, change the state of the variable play_status. If the data is in the playing state (PlayStatus.start), change it to the suspended state (PlayStatus.stop), and vice versa. The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 The logic used for forward and backward is the same. Here is an example for forward. First, if it is in the playing state, you need to pause the playback first, and then increase the data id to be loaded by one to read the point cloud and box. Note that the loaded point cloud and box are global variables. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
###  2.3. Open3D loads two windows simultaneously 

 Just create two Visualizers. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Both windows load the same point cloud object. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
 Keep refreshing the window, assigning the camera parameters of the first window to the second window 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573749533
  ```  
##  III. Code and test data 

 Link: https://pan.baidu.com/s/1yuSbk7gqBdYdJsK9xSjkNQ Extraction Code: w1yw 


#  I. Basic information 

 ![avatar]( 14151f7341b245088cb40e1559aace36.png) 

 Data download address: Stanford3dDataset_v1, the downloaded compressed package has 4.79G. After decompression, there are 6 folders, each folder represents a region  

 ![avatar]( 72532c9fe5b04887812b5016b85b35e3.png) 

 Each area folder is divided into subfolders for each room.  

 ![avatar]( 36d5856d90224b66befec29dc144cbe9.png) 

 Under each room folder is a point cloud file stored in txt format and Annotations, the label folder for that room.  

 ![avatar]( 3e31a9a79af0456aa0b13d34ad982ace.png) 

 The effect of opening the txt file in cloudcompare software  

 The Annotations folder contains the point cloud files for each component stored separately in this room, so the file name is the label for this part. 

 ![avatar]( 36328ff114d54d88886925dd29ecdca1.png) 

#  II. Data preprocessing 

##  2.1. Data cleaning 

 There are some errors in the directly decompressed data, mainly because a line of some files has a few more characters, such as Area_5\ office_19\ Annotations\ ceiling_1. Txt has a line of data containing characters, resulting in data operation failure. 

 ![avatar]( d62462dc9e19452eb5d9b0b1e76b8b05.png) 

##  2.2. Label visualization 

 The first section introduces that the label of S3DIS is actually the file name of the file of each component of the room. Here we merge the various components and then convert the file name to the label column. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 Where anno_paths txt is the following content 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 class_names is the following 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309573731356
  ```  
 Save it as txt and put it in the meta folder. 

 The effect is as follows: a single room 

 ![avatar]( 4692f6a0b21b451eb5d10318c39a9cb0.png) 

  Area1  Area_2  

 ![avatar]( 9e18d577301846a1b56a6a3c962198f0.png) 

 Area_3  

 ![avatar]( 8da0cd8fa4384f2eb3e2d01f6ded5237.png) 

 Area_4  

 ![avatar]( cbca8c898e3c401d80c98e8c34fdf6ad.png) 

 Area_5  

 ![avatar]( a300ef564fb84cdca7c363f0e399c064.png) 

 Area_6  


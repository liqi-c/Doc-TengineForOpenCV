# change log
### DNN module :

* OAL inference Engine Back-end([Tengine](https://github.com/OAID/Tengine)) : 
    - Support Arm v7/v8 platform inference acceleration. 
 Performance comparison:
 ![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-SingalA72.png)
# Wiki 
## Tengine User Guide  
 There are two ways to configure Tengine in OpenCV-DNN:
1. Tengine can be utilized from pre-built library, For user 
who already separately built Tengine. 
2. Tengine can be built from source code automatically, 
which is much easier to use. 
### Tengine Library Model
 Configurations as following should be added：
   ```
    -DOPENCV_LIBTENGINE_ROOT_DIR=/UserFileDir/Tengine-install-dir
    -DWITH_TENGINE=ON
   ``` 
**The following points maybe is useful：**
1. Tengine Compiled source files must be the following branche:
    >https://github.com/OAID/Tengine/tree/tengine-opencv
2. [Tengine Compiling instructions](
https://github.com/OAID/Tengine/wiki/Tengine%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B)
    
3. Tengine-library-dir directory structure
 ```
    /UserFileDir/Tengine-library-dir
    ├── include
    │   ├── cpu_device.h
    │   ├── tengine_c_api.h
    │   ├── tengine_c_compat.h
    │   └── tengine_operations.h
    └── lib
        └── libtengine.a
 ```
### Tengine Source Code Model
* Android : 
        You just need to add configuration as following and keep network 
connecting to GitHub. (*Tengine will be automatically downloaded and compiled*)：
   ```
    -DWITH_TENGINE=ON
   ```  
    (***Android NDK version must be no lower than r14***)
* linux :
    * Just add configuration as following 
    ``` 
    -DWITH_TENGINE=ON 
    ```
    * If you want to cross-compile Arm32 or Arm64, the following compiler need to be installed. 
        * Arm32:  arm-linux-gnueabihf
       ```
       sudo apt install g++-arm-linux-gnueabihf
       ```
        * Arm64:  aarch64-linux-gnu
        ```
        sudo apt install g++-aarch64-linux-gnu 
        ```

    
# opencv.org 

 **OpenCV.org description-version 0.1**

> OpenCV (OpenCV-DNN) supported CNN inference on Arm-based embedded devices but without in-depth performance optimization. Tengine will be integrated as a high-performance inference engine in the coming OpenCV 4.3, which will ignificantly enhance the CNN inference performance on Arm platform. 

## Trend
Due to low-cost, network bandwidth, power consumption, reliability and privacy issues, AI computing resources are migrating from cloud to terminal devices in many different industries, such as security, transportation, manufacturing, auto-driving, smart home and so on. Tens of thousands of devices need to be upgraded intelligently. 

Currently, most embedded devices use Arm IP, such as Cortex-A and Cortex-M series. However, it is difficult to implement deep Learning algorithms trained on x86 based server with Nvidia GPU on Arm-based hardware platform. The highest priority issue is the effectiveness and usability of inference speed.

##  Motivation
OpenCV (OpenCV-DNN) supports execute CNN inference on Arm-based embedded device without in-depth performance optimization. In order to enhance the CNN inference performance on the Arm platform, OpenCV integrate the Tengine as a high-performance arm computing library into the OpenCV DNN module, in the OpenCV 4.3 version for open source release. The Benchmark is demonstrated in following pictures.

![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-SingalA72.png)

![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-SingalA53.png)

![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-eaidk610.png)

## About Tengine
In addition to including a high-performance arm computing library, Tengine is also a application development platform for AIoT scenarios. Tengine is launched by <u>Open AI Lab</u> to solve the fragmentation problem of AIoT industrial chain and 
accelerating the landing of AI industrialization.

Tengine is specially designed for AIoT scenarios, and it has several features, such as cross hardware platform, heterogeneous scheduling, chip bottom acceleration, ultra-light weight, eployment tool chain. Compared with a variety of operating systems and deep learning algorithm framework, Tengine simplifies and accelerates the rapid migration of scene oriented AI algorithm on embedded edge devices, as well as the actual application deployment.
***More info in Tengine GitHub Homepage*** [https://github.com/OAID/Tengine](https://github.com/OAID/Tengine)
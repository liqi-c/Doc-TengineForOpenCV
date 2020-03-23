# Doc-TengineForOpenCV

# change log
### DNN module :

* [OAL](http://www.openailab.com/) inference Engine backend([Tengine](https://github.com/OAID/Tengine)) 
    - Support ARM v7/v8 platform inference  accelerate . 

    -  Performance comparison 

![image](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/tengine-opencv-benchmark20200320-eaidk610.png)
![image](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/tengine-opencv-benchmark20200320-SingalA72.png)

# Wiki 
## Tengine Use Descripe  
 There are Two ways to Configurite Tengine in OpenCV-dnn , one is use Tengine from binaries installation file , this may more difficulty for user which unfamiliar with Tengine. The Second way is build from Source Code , this way may more easy for user .
### Use Tengine binaries
 You just need to add configuretion ：
   ```
    -DOPENCV_LIBTENGINE_ROOT_DIR=/UserFileDir/Tengine-install-dir
    -DWITH_TENGINE=ON
   ``` 
**But there are several points to pay attention to**
1. Tengine Compiled source files must be the following branches
    >https://github.com/OAID/Tengine/tree/tengine-opencv
2. [Tengine Compiling instructions](
https://github.com/OAID/Tengine/wiki/Tengine%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B)
    
3. Tengine-install-dir architecture
 ```
    /UserFileDir/Tengine-install-dir
    ├── include
    │   ├── cpu_device.h
    │   ├── tengine_c_api.h
    │   ├── tengine_c_compat.h
    │   └── tengine_operations.h
    └── lib
        └── libtengine.a
 ```
### Build Tengine from source code
* Android : 
     You just need to add configuretion like below and keep network access to GitHub. (*Tengine will be auto download auto compile*)：
   ```
    -DWITH_TENGINE=ON
   ```  
    (***Android NDK version must greater than r14***)
* linux :
    * Just add configuretion like this 
    ``` 
    -DWITH_TENGINE=ON 
    ```
    * If you want to cross compile arm32 or arm64, you need to install the following compiler. 
        * Arm32:  arm-linux-gnueabihf
       ```
       sudo apt install g++-arm-linux-gnueabihf
       ```
       
        * Arm64:  aarch64-linux-gnu
        ```
        sudo apt install g++-aarch64-linux-gnu 
        ```


 **OpenCV.org description-version 0.1**

> OpenCV (OpenCV-DNN) support execute CNN inference on arm-based embedded device without in-depth performance optimization. In order to enhance the CNN inference performance on the Arm platform, OpenCV integrate the Tengine as a high-performance arm computing library into the OpenCV DNN module, in the OpenCV 4.3 version for open source release.


## Trend
More and more application scenarios will migrate AI computing from the cloud to terminal devices, whether in security, transportation, manufacturing , Medical or autonomous driving, smart home and other fields due to cost, latency, bandwidth, power consumption, reliability and privacy issues. Hundreds of millions of devices will be intelligently upgraded. An emerging huge IoT AI application market (AI-IoT) is emerging. 

Behind the huge market opportunities, most embedded devices use Arm IP, such as Cortex-A and Cortex-M series.  We'd like to perform inference tasks on an embedded device. However, it is difficulties to reimplement deep Learning algorithms on Arm based hardware, which is trained on x86 based server with Nvidia GPU. The highest priority issue is inference speed, hardly to meet the requirement of the application.

##  Motivation
OpenCV (OpenCV-DNN) support execute CNN inference on arm-based embedded device without in-depth performance optimization. In order to enhance the CNN inference performance on the Arm platform, OpenCV integrate the Tengine as a high-performance arm computing library into the OpenCV DNN module, in the OpenCV 4.3 version for open source release. See the Benchmark in the Following picture. 

[![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-SingalA72.png)](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/tengine-opencv-benchmark20200320-SingalA72.png)

[![image](https://github.com/liqi-c/Doc-TengineForOpenCV/raw/master/data/tengine-opencv-benchmark20200320-eaidk610.png)](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/tengine-opencv-benchmark20200320-eaidk610.png)

## About Tengine
Except a high-performance arm computing library, Tengine is a application development platform for AIoT scenarios, launched by [Open AI Lab](http://www.openailab.com/) which is dedicated to solving the fragmentation problem of AIoT industrial chain and accelerating the landing of AI industrialization. 

Tengine is specially designed for AIoT scenarios, and it has several features, such as cross platform, heterogeneous scheduling, chip bottom acceleration, ultra light weight and independent, and complete development and deployment tool chain. Tengine is compatible with a variety of operating systems and deep learning algorithm framework, which simplifies and accelerates the rapid migration of scene oriented AI algorithm on embedded edge devices, as well as the actual application deployment.

***More info. in Tengine GitHub Homepage*** https://github.com/OAID/Tengine

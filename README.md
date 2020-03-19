# Doc-TengineForOpenCV

# change log
### DNN module :

* [OAL](http://www.openailab.com/) inference Engine backend([Tengine](https://github.com/OAID/Tengine)) 
    - Support ARM v7/v8 platform inference  accelerate . 

    -  Performance comparison 
![image](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/performance.png)

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




# Doc-TengineForOpenCV

# change log
### DNN module :

* OAL inference Engine backend([Tengine](https://github.com/OAID/Tengine)) : 
    - Support ARM v7/v8 platform inference  accelerate . 

    -  Performance comparison 
![image](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/performance.png)

# Wiki 
## Tengine Build descripe   
* Android : 
    If  you know how to build OpenCV in android platform , you just need add -DWITH_TENGINE=ON .   
    ``` Notice : Android NDK version must greater than r14 ```
* linux :
    Just add -DWITH_TENGINE=ON . We use cross-compilation toolchain as OpenCV configure , through CC Pass to Tengine. 
    * Arm32:  arm-linux-gnueabihf
       ```
       sudo apt install g++-arm-linux-gnueabihf
       ```
       
    * Arm64:  aarch64-linux-gnu
        ```
        sudo apt install g++-aarch64-linux-gnu 
        ```
    
# opencv.org 



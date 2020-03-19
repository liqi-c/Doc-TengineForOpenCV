# Doc-TengineForOpenCV

# change log
### DNN module :

* OAL inference Engine backend([Tengine](https://github.com/OAID/Tengine)) : 
    - Support ARM v7/v8 platform inference  accelerate . 

    -  Performance comparison (***CPU : armA53 ,A72 ; Min time:ms***)
![image](https://github.com/liqi-c/Doc-TengineForOpenCV/blob/master/data/performance.png)
| Models | ArmA53-befer   | ArmA53-now  | ArmA72-befer  | ArmA72 -now  | 
| ---       | ---                  | ---               | ---                 | ---                 |
| MobileNet1.0 |              |                    |                      |
| SqueeseNet1.1 |  |  |  |
| ResNet18 |  |  |  |
| VGG16 |  |  |  |

# Wiki 
```Tengine Build descripe  ``` 
* Android : 
    If  you know how to build OpenCV in android platform , you just need add -DWITH_TENGINE=ON .   
    ``` Notice : Android NDK version must greater than r14 ```
* linux :
    Just add -DWITH_TENGINE=ON . We use cross-compilation toolchain as OpenCV configure , through CC Pass to Tengine. 
    
    
# opencv.org 



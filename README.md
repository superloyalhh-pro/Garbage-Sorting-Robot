# Garbage-Sorting-Robot
#### A robot that recognizes and classifies garbages in the field, independently 
#### 垃圾分拣车用于自主识别场地的垃圾并将其正确分拣到相应的垃圾堆放区。
#### 小车分为上下两层，上层搭载的是以Jetson Nano为中心的ROS层上位机，下层搭载的是以STM32为中心的下位机。垃圾堆放区不同的颜色代表不同类的垃圾。
- 蓝色：可回收垃圾
- 绿色：厨余垃圾
- 红色：有害垃圾
- 棕色：其他垃圾

我们的项目可以分解为四个方面，底层控制(Base Control)，目标检测和追踪(Object detection & tracking)，颜色检测和追踪(Color detection & tracking)，自主导航(Navigation)。
在底层控制(Base Control)中，我们从四个层面来阐述各环节的联动控制。

- 首先是各模块的12V,5V,3.3V电力供应；然后是下位机向上位机实时发送传感器数据、上位机向下位机发送运动和控制命令；最后我们阐述用Ros中的TF包将各传感器的数据在不同参考系间进行转换。
- 在目标检测和追踪(Object detection & tracking)中，我们从两个层面来阐述垃圾识别分类的原理和方法。目标检测：我们在实际羽毛球场地拍摄垃圾图像并自主贴标签制作训练集训练模型，并用训练出来的模型检测视野内存在的目标垃圾；目标追踪：对视野内的某一目标垃圾进行追踪。
- 在颜色检测和追踪(Color detection & tracking)中，我们从两个层面来阐述如何识别垃圾堆放区域。颜色检测：用OpenCV来进行单颜色检测进而识别相应的垃圾堆放区域。颜色追踪：对垃圾堆放区域进行追踪。
- 在自主导航(Navigation)中，利用PID控制实现机器人自主从场地中一点移动到另一点。

![image](https://github.com/superloyalhh-pro/Garbage-Sorting-Robot/blob/main/Project/Robot.jpg)

# CCUT机甲大师步兵代码-李伟豪

## 一.简介&&日志

2024年11月07日

这个项目开始主要是想要自己构建一套代码，第一是让自己能够更好的调试我们的步兵，第二是留给学弟学妹一套代码，让他们能够基于我的代码进行修改和调试，我基本会按照linux的编码规范进行编写。

2024年11月09日

今天完成了遥控器数据的解析，并且创建了一个RC_task任务专门用来获取遥控器数据，但是在大疆开源代码中，并没有单独为遥控器创建一个任务，可能是因为串口中断的原因，遥控器数据是一直在解析的，但是那些初始化操作是要完成的，所以应该是在底盘任务或者云台任务中体现，这里注意一下，串口中断函数在f4xx.it文件中我将hal库自动生成的串口中断函数注释了，暂时我也不知道原因，这个中断服务函数写在了RC_task中。

2024年11月10日

今天凌晨想着加一个git的版本控制，但是linux下一直无法实现，那就只能在windows下搞定了，弄了半天还不如早点放弃。其实搞东西也是这样，一遍遍猜想试错，下次上传就不只是上传一个markdown了，更新日志就是新增的的内容

## 二.文件目录

* App(用于freertos的相关任务的执行和实现)
* Board（主要是c板上具有的外设驱动代码，提供api给任务函数调用）
* Core
* Drivers
* Middlewares
* 

每个文件夹里面都有一个Inc,Src用于存放对应的.h和.c文件

## 三.编译&&下载

1.开发方式采用Cubemax+makefile+openocd的方式

2.如何编译

在工程目录下打开终端输入

```
make -j8
```

3.下载：编译完成后，在build文件夹中找到hex文件，下载到c板上就行

## 四.注意事项

1.必须配置好make环境和openocd的环境，具体配置参考网上教程或者我的教程

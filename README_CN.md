基于Sipeed Maix one平台的micropython
======================================
<p align="center">
  <img src="http://pgeza64pd.bkt.clouddn.com/dan-board.jpg" alt="Sipeed Maix one"/>
</p>

MaixPy介绍
------------

MaixPy基于Sipeed Maix One平台适配的micropython,支持Sipeed M1上的多种外设，旨在让编程更加简单。

MaixPy基于K210裸机sdk编写,版本Python 3.4

更多关于MaixPy的内容，请到http://maixpy.sipeed.com/ 查看了解


目录架构
------------

MaixPy主要目录架构:

- py/ --  核心Python实现，包括编译器，运行时和核心库。

- mpy-cross/ --   MicroPython交叉编译器，用于将脚本转换为预编译的字节码。 

- ports/k210-standalone/ -- 基于k210平台sdk的micropython移植代码

- tests/ -- 测试框架及测试脚本 

- docs/ -- 基于rst格式的micropython用户文档，HTML文档的链接 http://docs.micropython.org 

平台移植代码目录架构：

- board-drivers/  存放板载模块驱动代码

- buildin-py/ 固件内置microPython脚本

- mpy-mod/ micropython模块代码

- spiffs/ spiffs文件系统源码

- spiffs-port/ spiffs移植配置代码

- kendryte-standalone-sdk/ 在使用构建脚本后生成的k210 sdk

构建及编译
--------------------

构建代码:

    $ git clone git@github.com:sipeed/MaixPy.git #下载sdk
	$ cd port/k210-standalon/ #进入平台代码目录
	$ make build #在第一次使用的情况下,构建平台代码

编译代码:

	$ make CROSS_COMPILE=/your_compiler_path 
	

`your_compiler_path`为编译器路径，编译器可以查看http://dan.lichee.pro/ 了解

编译完成将在该目录下生成micropython.bin文件，将该文件烧录到Sipeed Maix One套件即可,烧录方法可以查看http://dan.lichee.pro/ 了解
	

贡献
------------

MaixPy是一个开源项目，欢迎贡献，MicroPython是根据MIT许可证获得许可的，所有贡献都应遵循此许可证。

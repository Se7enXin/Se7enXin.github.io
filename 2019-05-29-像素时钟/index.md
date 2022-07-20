# DIY一个炫酷的像素时钟


![](/images/awtrix.jpeg)

## 一、介绍

#### 1、[官网Docs](https://docs.blueforcer.de/#/v2/)

#### 2、简介

![wifi像素时钟介绍](/images/wifi像素时钟介绍.PNG)

    wifi模块作为客户端与服务器连接同一wifi
    客户端尝试与服务器建立连接，成功建立连接后客户端向服务器发出信号
    服务器收到信号后向客户端发送时间相关的信息，
    客户端收到后将时间信息转换为8x32柔性屏对应的指令并发送，柔性屏收到后显示

## 二、配件清单

### 1、ESP8266 WIFI模块 CP2102 ESP-12E（￥27.83）

### 2、8x32 WS2812B 柔性软屏（￥114）

说起这个柔性软屏就很厉害了，它不需要驱动，一共256个点，每个点都带有一块芯片和LED，
平均算下来，芯片+LED+电容不到5毛钱

### 3、外壳（￥30）

如何封装每个人都有自己的喜好，我这里选择的低成本亚克力外壳

在淘宝找店家做的，最好多问几家，有的给的价格虚高

![黑色透明外壳](/images/黑色透明外壳.PNG)

### 4、树莓派（可选）

### 5、3D打印的光栅（可选）

光栅建议选择深色不透明材料

[3D图纸下载](https://www.thingiverse.com/thing:2791276)

## 三、软件

### 1、Controller

#### （1）下载Visual Studio Code，安装Platform.IO

[How to install Platform.IO](https://platformio.org/install/ide?install=vscode)

#### （2）下载wifi模块固件，并在Platform.IO中打开

[Download AWTRIX2.0-Controller](https://github.com/awtrix/AWTRIX2.0-Controller)

![](/images/Snipaste_2019-05-29_17-50-26.png)

![](/images/Snipaste_2019-05-29_17-52-41.png)

#### (3) 设置服务器信息

打开`awtrix-conf.h`，修改以下内容：

```c
// Wifi Config
const char *ssid = "YourSSID";
const char *password = "YourPassword";
char *awtrix_server = "192.168.178.39";
```

|||
|-|-|
|ssid|wifi名称|
|password|wifi密码|
|awtrix_server|服务器IP|

#### (4) 连接wifi模块，刷写固件

wifi连接micro USB线后，在`Platform.IO`的`Devices`中，应该会找到对应的设备，如果没有，可以尝试安装下面这个驱动：

[驱动](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)

`Devices`中找到对应设备后，点击刷写按钮完成刷写

![](/images/Snipaste_2019-05-29_18-08-59.png)

### 2、Server

Server可以运行在任意平台，只要支持Java8就可以，对别的没有要求。

Server的部署见[官方文档](https://docs.blueforcer.de/#/v2/host)

## 四、组装


## 五、演示

## 六、参考













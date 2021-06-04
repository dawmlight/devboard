# 开发板名称：
# Taurus AI Camera开发套件



#### 开发板描述：
Taurus AI Camera开发套件是江苏润和软件股份有限公司于2020年9月推出的OpenHarmony系列开发板之一，支持OpenHarmony 1.1.0 LTS开源版本。

 

##### 关键词: 
AI Camera，Hi3516DV300，全栈轻量化，完备的图形栈和多媒体能力，分布式能力

发行版@ohos/hispark_taurus 版本1.0.4 发布于2021-04-08 09:53:07




## MCU/处理器

1.双核Cortex-A7 MP2 @ 900MHz处理器

2.集成新一代 ISP、业界最新的H.265视频压缩编码器

3.集成高性能 NNIE 引擎，1.0TOPS

4.集成POR、RTC、Audio Codec以及待机唤醒电路



## 开发板介绍

### 开发板概述

Taurus AI Camera开发套件基于海思Hi3516DV300芯片设计，支持OpenHarmony包含主板、Sensor板、底板和灯板，配有触摸显示屏。

Taurus AI Camera开发套件技术参数如下：

![AI Camera产品参数](C:\Users\jz\Desktop\产品参数\产品参数\AI Camera产品参数.png)

### 开发板功能

Taurus AI Camera开发套件可以实现图像编解码显示的基础功能，如图像采集、多路编码、音视频存储传输、音视频显示回放等应用场景；可以通过SVP （Smart Vision Platform）特性及卷积神经网络模型，实现AI计算机视觉基础功能，如人脸检测识别、车牌识别等应用场景。

Taurus AI Camera开发套件可以通过搭积木的方式组成USB计算棒、AI Camera以及AI视频分析记录仪等。



## 开发板详情

一、主板

1.主板正面

•基于Hi3516DV300的最小系统：32bit/1GB内存，8GB eMMC存储空间

•预留算法加密IC

•双色指示灯

![image-20210526192951835](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526192951835.png)

2.主板反面

•UART0 Debug调试接口

•Micro HDMI接口

•Type C通信接口，同时满足产品5V供电需求(与Sensor板兼容设计)

•2路自定义按键及软件更新按键

![image-20210526193008429](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526193008429.png)

二、镜头板

1.镜头板正面

•UART0 Debug调试接口

•Micro HDMI接口

•Type C通信接口，同时满足产品5V供电需求(与Sensor板兼容设计)

•2路自定义按键及软件更新按键



![image-20210526190757142](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526190757142.png)

2.镜头板反面

•单声道差分mic接口

•适配8Ω/2W 1.25㎜端子小喇叭

•Type C通信接口，同时满足产品5V供电需求（与Core板兼容设计）

![image-20210526190910929](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526190910929.png)

三、灯板

1.灯板正面

•红外补光灯 x 2

•高灵敏度光敏二极管

•指示灯 x 1

•单声道驻极体表贴Mic

![image-20210526190930690](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526190930690.png)

2.灯板反面

•蜂鸣器

•NFC模组扩展接口

•I2C接口x2

![image-20210526190946026](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526190946026.png)

四、扩展板

1.扩展板正面

•Type C 5V/3A 供电接口

•Ethernet接口，支持RMII模式

•标准JTAG接口

•PWM x1

•ADC x1

•GPIO x4

•I2C x 1

•UART x 1

![image-20210526191020727](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526191020727.png)

2.扩展板反面

•兼容4寸、5.5寸LCD屏接口

•TP接口

![image-20210526191043979](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526191043979.png)



## 应用案例场景

### 开发板应用场景

Taurus AI Camera开发套件适用于智能摄像、安防监控、车载记录仪等。

### 上手指南

#### 环境搭建

1.Windows 环境准备

系统要求：Windows 10 64位系统

- [ ] 安装Visual Studio Code
- [ ] 安装Python
- [ ] 安装Node.js
- [ ] 安装hpm
- [ ] 安装DevEco Device Tool插件

2.编译环境准备

##### 将Linux shell改为bash

查看shell是否为bash，在终端运行如下命令

```
ls -l /bin/sh
```

如果显示为“/bin/sh -> bash”则为正常，否则请按以下方式修改：

**方法一**：在终端运行如下命令，然后选择 no。

```
sudo dpkg-reconfigure dash
```

**方法二**：先删除sh，再创建软链接。

```
sudo rm -rf /bin/shsudo ln -s /bin/bash /bin/sh
```

##### 安装编译依赖基础软件（仅Ubuntu 20+需要）

执行以下命令进行安装：

```
sudo apt-get install build-essential && sudo apt-get install gcc && sudo apt-get install g++ && sudo apt-get install make && sudo apt-get install zlib* && sudo apt-get install libffi-dev
```

##### 安装文件打包工具

1. 打开Linux编译服务器终端。

2. 运行如下命令，安装dosfstools。

   ```
   sudo apt-get install dosfstools
   ```

3. 运行如下命令，安装mtools。

   ```
   sudo apt-get install mtools
   ```

4. 运行如下命令，安装mtd-utils。

   ```
   sudo apt-get install mtd-utils
   ```

##### 安装hc-gen

1. 打开Linux编译服务器终端。

2. [下载hc-gen工具](https://repo.huaweicloud.com/harmonyos/compiler/hc-gen/0.65/linux/hc-gen-0.65-linux.tar)。

3. 解压hc-gen安装包到Linux服务器~/hc-gen路径下。

   ```
   tar -xvf hc-gen-0.65-linux.tar -C ~/
   ```

4. 设置环境变量。

   ```
   vim ~/.bashrc
   ```

   将以下命令拷贝到.bashrc文件的最后一行，保存并退出。

   ```
   export PATH=~/hc-gen:$PATH
   ```

5. 生效环境变量。

   ```
   source ~/.bashrc
   ```

##### 安装Java 虚拟机环境

1. 打开Linux编译服务器终端。

2. 安装Java运行时环境（JRE）。

   ```
   sudo apt-get install default-jre
   ```

3. 安装Java sdk开发工具包。

   ```
   sudo apt-get install default-jdk
   ```




#### 烧录步骤

Taurus AI Camera开发套件的代码烧录支持USB烧录、网口烧录和串口烧录三种方式，此处仅以网口烧录为例进行说明。

1. 请连接好电脑和待烧录开发板，以Hi3516DV300为例，需要同时连接串口、网口和电源，具体可参考[Hi3516开发板介绍](https://device.harmonyos.com/cn/docs/start/introduce/oem_camera_start_3516-0000001052670587)。

2. 打开电脑的设备管理器，查看并记录对应的串口号。

   说明

   如果对应的串口异常，请根据[Hi3516/Hi3518系列开发板串口驱动安装指导](https://device.harmonyos.com/cn/docs/ide/user-guides/hi3516_hi3518-drivers-0000001050743695)安装USB转串口的驱动程序。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.05535958582408686672017757251828:50520516020516:2800:4D35FB536AA21E9507F4110727876DB49570CBA39A242E40A6EAA10342189071.png?needInitFileName=true?needInitFileName=true)

3. 打开DevEco Device Tool，在Projects中，点击**Settings**打开工程配置界面。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.85745354122154418329231237397830:50520516020516:2800:5BD322D48B01FF65CBC8F95B28B2C2FB338D0647A20E11B3CE204334233BDACD.png?needInitFileName=true?needInitFileName=true)

4. 在“hi3516dv300”页签，设置烧录选项，包括upload_port、upload_partitions和upload_protocol。

   - upload_port：选择步骤[2](https://device.harmonyos.com/cn/docs/start/introduce/oem_camera_start_first_example-0000001051610926#ZH-CN_TOPIC_0000001052906247__zh-cn_topic_0000001056443961_li142386399535)中查询的串口号。
   - upload_protocol：选择烧录协议，固定选择“hiburn-net”。
   - upload_partitions：选择待烧录的文件，默认情况下会同时烧录fastboot、kernel、rootfs和userfs。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.15591883240453428498036170088931:50520516020516:2800:178EA4F9ACD4BBD6BAF3D0AC24E2248E707DD70F535235E38A675F8F46D5934C.png?needInitFileName=true?needInitFileName=true)

5. 检查和设置连接开发板后的网络适配器的IP地址信息，设置方法请参考[设置Hi3516网口烧录的IP地址信息](https://device.harmonyos.com/cn/docs/ide/user-guides/set_ipaddress-0000001141825075)。

6. 设置网口烧录的IP地址信息，设置如下选项：

   - upload_net_server_ip：选择[5](https://device.harmonyos.com/cn/docs/start/introduce/oem_camera_start_first_example-0000001051610926#ZH-CN_TOPIC_0000001052906247__zh-cn_topic_0000001056443961_li1558813168234)中设置的IP地址信息。例如192.168.1.2
   - upload_net_client_mask：设置开发板的子网掩码，工具会自动根据选择的upload_net_server_ip进行设置。例如255.255.255.0
   - upload_net_client_gw：设置开发板的网关，工具会自动根据选择的upload_net_server_ip进行设置。例如192.168.1.1
   - upload_net_client_ip：设置开发板的IP地址，工具会自动根据选择的upload_net_server_ip进行设置。例如192.168.1.3

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.16739402746351635804045142486411:50520516020516:2800:A639C63E90CDE036FA62211FD98FF6BB5FAB78B15ED0A8B262F4D7C8FE37C78E.png?needInitFileName=true?needInitFileName=true)

7. 修改待烧录文件（对应hi3516dv300_fastboothi3516dv300_kernel、hi3516dv300_rootfs和hi3516dv300_userfs页签）的设置，默认情况下，DevEco Device Tool已针对Hi3516系列开发板进行适配，无需单独修改。如果需要修改，请在New Option中，选择对应的修改项进行更改。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.46834501931897028107505926963836:50520516020516:2800:601D74DB5D6931113F3F9659CBC0DFD84CD4884B534D0DBA31EF74369D324743.png?needInitFileName=true?needInitFileName=true)

8. 所有的配置都修改完成后，在工程配置页签的顶部，点击**Save**进行保存。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.28415927905155099650582332139606:50520516020516:2800:2B95B2E848CF1A57B4B077E8FF00B4777B29ECA0229D4E7EE59E7F41A0154B61.png?needInitFileName=true?needInitFileName=true)

9. 打开工程文件，点击![img](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.92035228054223210346412869972147:50520516020516:2800:2F284B527482E79409720F18402E0401D0F1F8C511F3671F913BFBE96FFCBBA3.png?needInitFileName=true?needInitFileName=true)图标，打开DevEco Device Tool界面，在“PROJECT TASKS”中，点击env:hi3516dv300下的**Upload**按钮，启动烧录。

   ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.82140076635424355976011789203060:50520516020516:2800:4D0A4F1CB17EC80A0BC99FDF1ACD0A076CC77047B9EBA1FDA8913D35D467092B.png?needInitFileName=true?needInitFileName=true)

10. 启动烧录后，显示如下提示信息时，请重启开发板（下电再上电）。

    ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.44971636649530591166091495400133:50520516020516:2800:1840B25E02C1212B9432E70A64BF96084915A87F59BCF259B2EEF8AEBFE4BFC6.png?needInitFileName=true?needInitFileName=true)

11. 重新上电后，启动烧录，界面提示如下信息时，表示烧录成功。

    ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194627.14104265774020844376475192925116:50520516020516:2800:7EBF5C5541A5C5213A91DDA6276DABFECA39236B53E6CB864F657A3397A827C5.png?needInitFileName=true?needInitFileName=true)



### 代码样例说明

1. 新建目录及源码

   新建**applications/sample/camera/apps/src/helloworld.c**目录及文件，代码如下所示，用户可以自定义修改打印内容（例如：修改OHOS为World）。当前应用程序可支持标准C及C++的代码开发。

   ```c++
   #include <stdio.h>
   
   int main(int argc, char **argv)
   {
       printf("\n************************************************\n");
       printf("\n\t\tHello OHOS!\n");
       printf("\n************************************************\n\n");
   
       return 0;
   }
   ```

2. 新建编译组织文件

   新建**applications/sample/camera/apps/BUILD.gn**文件，内容如下所示：

   ```c++
   import("//build/lite/config/component/lite_component.gni")
   lite_component("hello-OHOS") {
     features = [ ":helloworld" ]
   }
   executable("helloworld") {
     output_name = "helloworld"
     sources = [ "src/helloworld.c" ]
     include_dirs = []
     defines = []
     cflags_c = []
     ldflags = []
   }
   ```

3. 添加新组件

   修改文件**build/lite/components/applications.json**，添加组件hello_world_app的配置，如下所示为applications.json文件片段，"##start##"和"##end##"之间为新增配置（"##start##"和"##end##"仅用来标识位置，添加完配置后删除这两行）：

   ```c++
   {
     "components": [
       {
         "component": "camera_sample_communication",
         "description": "Communication related samples.",
         "optional": "true",
         "dirs": [
           "applications/sample/camera/communication"
         ],
         "targets": [
           "//applications/sample/camera/communication:sample"
         ],
         "rom": "",
         "ram": "",
         "output": [],
         "adapted_kernel": [ "liteos_a" ],
         "features": [],
         "deps": {
           "components": [],
           "third_party": []
         }
       },
   ##start##
       {
         "component": "hello_world_app",
         "description": "Communication related samples.",
         "optional": "true",
         "dirs": [
           "applications/sample/camera/apps"
         ],
         "targets": [
           "//applications/sample/camera/apps:hello-OHOS"
         ],
         "rom": "",
         "ram": "",
         "output": [],
         "adapted_kernel": [ "liteos_a" ],
         "features": [],
         "deps": {
           "components": [],
           "third_party": []
         }
       },
   ##end##
       {
         "component": "camera_sample_app",
         "description": "Camera related samples.",
         "optional": "true",
         "dirs": [
           "applications/sample/camera/launcher",
           "applications/sample/camera/cameraApp",
           "applications/sample/camera/setting",
           "applications/sample/camera/gallery",
           "applications/sample/camera/media"
         ],
   ```

4. 修改单板配置文件

   修改文件**vendor/hisilicon/hispark_taurus/config.json**，新增hello_world_app组件的条目，如下所示代码片段为applications子系统配置，"##start##"和"##end##"之间为新增条目（"##start##"和"##end##"仅用来标识位置，添加完配置后删除这两行）：

   ```c++
     {
           "subsystem": "applications",
           "components": [
             { "component": "camera_sample_app", "features":[] },
             { "component": "camera_sample_ai", "features":[] },
   ##start##
             { "component": "hello_world_app", "features":[] },
   ##end##
             { "component": "camera_screensaver_app", "features":[] }
           ]
         },
   ```

## 创建新发行版

创建一个新的发行版继承自本发行版，并执行发行命名

```
hpm init -t dist
hpm i @ohos/hispark_taurus
hpm dist
```


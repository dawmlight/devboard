# 开发板名称：
Aries IPC开发套件



#### 开发板描述：
Aries IPC开发套件是江苏润和软件股份有限公司于2020年9月推出的OpenHarmony系列开发板之一，支持OpenHarmony 1.1.0 LTS开源版本。



##### 关键词: 
IP Camera，Hi3518EV300，快速启动、高实时性多进程内核，摄像头虚拟化为手机硬件资源，支持灵活控制和切换

发行版@ohos/hispark_aries 版本1.0.3 发布于2021-04-08 09:49:25




## MCU/处理器

1.集成新一代ISP，优化后的编码前图像处理算法和新一代H.264编码器

2.集成DRAM、POR、RTC、Audio Codec、Sensor电平转换以及各种时钟输出



## 开发板介绍

### 开发板概述

Aries IPC开发套件基于海思Hi3518EV300芯片设计，支持OpenHarmony，采用先进低功耗工艺和低功耗架构，使其在低码率、高画质、低功耗等方面引领行业水平。



Aries IPC开发套件技术参数如下：

![IPC产品参数](C:\Users\jz\Desktop\产品参数\产品参数\IPC产品参数.png)



### 开发板功能

Aries IPC开发套件具备高清监控能力，1920*1080/25fps，水平355°/垂直90°旋转，无死角监控；具备射频及抗干扰能力，传输稳定，强接收灵敏度，强射频性能，远距离传输信号不产生衰减，不受外界干扰因素影响；具备AI智能识别能力，支持AI自动人形跟踪、高灵敏度无死角自动跟踪无误报；支持云网站、云储存、设备分享，使用客户端集中管理，支持OpenHarmony场景应用及无感配网，具备生态优势。



## 开发板详情

1.ICR：双滤光片切换器，是用于让滤光片白天切换到不感红外滤光片和晚上切换到感红外滤光片的红外摄像机配件。

2.LED发光二极管

![IPC主板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Aries IPC开发套件信息\Aries IPC开发套件信息\img\IPC主板.png)



## 应用案例场景

### 开发板应用场景

Aries IPC开发套件可广泛应用于智能摄像、安防监控、车载记录仪等。

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




#### 烧录步骤

11. Hispark Aries 开发板的代码烧录仅支持USB烧录方式。

    1. 请连接好电脑和待烧录开发板，以Hi3518EV300为例，需要同时连接串口和USB口，具体可参考[Hi3518开发板介绍](https://device.harmonyos.com/cn/docs/start/introduce/oem_camera_start_hi3518-0000001050170473)。
    
    2. 打开电脑的设备管理器，查看并记录对应的串口号。
    
       说明
    
       如果对应的串口异常，请根据[Hi3516/Hi3518系列开发板串口驱动安装指导](https://device.harmonyos.com/cn/docs/ide/user-guides/hi3516_hi3518-drivers-0000001050743695)安装USB转串口的驱动程序。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.52365415691567664777350058772354:50520516020516:2800:81B1E5E9F1318B9827C807C2D97C6FEFFFC18C38052DAD3EAEC85D11B8636988.png?needInitFileName=true?needInitFileName=true)
    
    3. 打开DevEco Device Tool，在Projects中，点击**Settings**打开工程配置界面。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.40539297153829288849129064875834:50520516020516:2800:B9299E687B45B62EA337BA93F02996E15CEC1160D45F6818C2A25C8F5B8B2DCF.png?needInitFileName=true?needInitFileName=true)
    
    4. 在“hi3518ev300”页签，设置烧录选项，包括upload_port、upload_partitions和upload_protocol。
    
       - upload_port：选择步骤[2](https://device.harmonyos.com/cn/docs/start/introduce/oem_camera_start_example-0000001051610926#ZH-CN_TOPIC_0000001053422339__zh-cn_topic_0000001057313128_li46411811196)中查询的串口号。
       - upload_protocol：选择烧录协议，固定选择“hiburn-usb”。
       - upload_partitions：选择待烧录的文件，默认情况下会同时烧录fastboot、kernel、rootfs和userfs。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.13737116930267161410779696800769:50520516020516:2800:59C186ED20762ED0017FDF7FAE9BDA9809FB49116AD70FD7A2DCBBFF3DB9F654.png?needInitFileName=true?needInitFileName=true)
    
    5. 修改待烧录文件（对应hi3518ev300_fastboot、hi3518ev300_kernel、hi3518ev300_rootfs和hi3518ev300_userfs页签）的设置，默认情况下，DevEco Device Tool已针对Hi3518系列开发板进行适配，无需单独修改。如果需要修改，请在New Option中，选择对应的修改项进行更改。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.17265060977293900922962712935731:50520516020516:2800:84753B789E54EFEB605C25565745C2CB310955A4997A53FDD40543460146B2A0.png?needInitFileName=true?needInitFileName=true)
    
    6. 所有的配置都修改完成后，在工程配置页签的顶部，点击**Save**进行保存。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.19583728842553082292962958159625:50520516020516:2800:1578E360006E4A2020D3657DCA0C1050E9CECB126A501F84CD14DDBD6BC68D7C.png?needInitFileName=true?needInitFileName=true)
    
    7. 打开工程文件，点击![img](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.29403477852225996918775627782925:50520516020516:2800:E5DE6620FCD04F37EFED1A5B223057627C2023607CE980A607FBF229CFE68765.png?needInitFileName=true?needInitFileName=true)图标，打开DevEco Device Tool界面，在“PROJECT TASKS”中，点击partition:hi3518ev300_fastboot下的**Erase**按钮，擦除U-Boot。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.87792736313205284996067795540602:50520516020516:2800:896C6860085A66CECA81A9FD622DC2C7C27480546FBC4623999AC0E25718634F.png?needInitFileName=true?needInitFileName=true)
    
    8. 执行**Erase**擦除操作后，显示如下提示信息时，请重启开发板（下电再上电）。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.54209087121259714036721640330097:50520516020516:2800:BD48732C9F57E6689DED7D2C2CC13133DB58D83A859F3AFD30425B82C31A546A.png?needInitFileName=true?needInitFileName=true)
    
    9. 重新上电后，显示如下信息时，表示擦除U-Boot成功。
    
       ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.62175345350426475370147843837607:50520516020516:2800:59C9909CB29F4F6FDEACE50D689396DD024EA6F82C14F487464CA6EE4BCB6840.png?needInitFileName=true?needInitFileName=true)
    
    10. 擦除完成后，点击env:hi3518ev300下的**Upload**按钮，启动烧录。
    
        ![img](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.78943076427520194620700647665799:50520516020516:2800:7474DB1751C04C94DEE342F5DFA7679AA1E612C4399CAF1ECB7AE712A0C59C30.png?needInitFileName=true?needInitFileName=true)
    
    11. 启动烧录后，界面提示如下信息时，表示烧录成功。
    
        ![点击放大](https://alliance-communityfile-drcn.dbankcdn.com/FileServer/getFile/cmtyPub/011/111/111/0000000000011111111.20210514194629.84669337370580781776230360514259:50520516020516:2800:611E2FA8480EB5B1BF9645943952D3FC30E88D937BFEEC8EF8E0374B74DADC5F.png?needInitFileName=true?needInitFileName=true)





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

   修改文件**vendor/hisilicon/hispark_aries/config.json**，新增hello_world_app组件的条目，如下所示代码片段为applications子系统配置，"##start##"和"##end##"之间为新增条目（"##start##"和"##end##"仅用来标识位置，添加完配置后删除这两行）：

   ```c++
     {
           "subsystem": "applications",
           "components": [
   ##start##
             { "component": "hello_world_app", "features":[] },
   ##end##
             { "component": "camera_sample_app", "features":[] }
   
           ]
         },
   ```

## 创建新发行版

创建一个新的发行版继承自本发行版，并执行发行命名

```
hpm init -t dist
hpm i @ohos/hispark_aries
hpm dist
```


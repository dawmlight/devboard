# 开发板名称：
Neptune开发板



#### 开发板描述：
Neptune开发板是江苏润和软件股份有限公司推出的OpenHarmony系列开发板之一，发布于2020年12月推出，支持OpenHarmony 1.1.0 LTS开源版本。



##### 关键词: 
Wi-Fi & 蓝牙双模，W800，无线蓝牙键盘

发行版:@hihope/neptune_iot 版本1.0.1 发布于2021-01-18 10:48:21




## MCU/处理器

1. 集成XT804 CPU 处理器，工作频率240MHz，内置DSP、浮点运算单元与TEE安全引擎
2. MCU内置 Tee 安全引擎，代码可区分安全世界/非安全世界
3. 集成 SASC/TIPC，内存及内部模块/接口可配置安全属性，防止非安全代码访问
4. 集成硬件加解密模块：RC4 256、AES 128、DES/3DES、SHA1/MD5、CRC32、TRNG、2048 RSA



## 开发板介绍

### 开发板概述

Neptune开发板基于联盛德W800芯片设计，是一款高性价比Wi-Fi & 蓝牙双模SoC开发板，支持标准的802.11 b/g/n协议，内置完整的TCP/IP协议栈，集成蓝牙基带处理器，支BT/BLE4.2协议。

Neptune开发板技术参数如下：

![Neptune产品参数](C:\Users\jz\Desktop\产品参数\产品参数\Neptune产品参数.png)

### 开发板功能

Neptune开发板采用SMD封装，可通过标准SMT设备实现产品的快速生产，为客户提供高可靠性的连接方式，特别适合自动化、大规模、低成本的现代化生产方式，方便应用于各种物联网硬件终端场合。



## 开发板详情



![image-20210526202333944](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526202333944.png)

![image-20210526202327696](C:\Users\jz\AppData\Roaming\Typora\typora-user-images\image-20210526202327696.png)



## 应用案例场景

### 开发板应用场景

Neptune开发板具备极强的生态优势，可广泛适用于智能家电、智能家居、智能玩具、无线音视频、工业控制、医疗监护等物联网领域。



### 上手指南

#### 环境搭建

1.首先配置linux编译环境：安装python3.7.5以上的版本，ninja、gn、git、csky-elfabiv2-gcc、llvm等编译工具链

2.然后安装Visual Studio Code进行代码编辑


#### 烧录步骤

1.首先安装烧录软件SecureCRSecureFXPortable.tar

2.然后在PC端按住ESC，主板按下RST键，工具界面出现ccccc时，点击菜单栏中[Transfer]，选择[Send Xmodem]，然后选择要烧录的版本即可。

3.最后烧写成功后，工具界面依然出现ccccc，这时按下RST键，系统启动。

### 代码样例说明

1.新建目录及源码

新建**applications/sample/wifi-iot/app/hello/helloworld.c**目录及文件，代码如下所示，用户可以自定义修改打印内容。当前应用程序可支持标准C及C++的代码开发。

```
#include <stdio.h>

void PrintTask(const char *arg)
{
    (void)arg;
    printf("\n************************************************\n");
    printf("\nHello HarmonyOS!\n");
    printf("\n************************************************\n\n");

    return 0;
}
```

2.新建和修改编译组织文件
新建**applications/sample/wifi-iot/app/hello/BUILD.gn**文件，内容如下所示：
static_library("hello") {
    sources = [
        "helloworld.c"
    ]

    include_dirs = [
        "//utils/native/lite/include",
        "//kernel/liteos_m/kal/cmsis",
        "//base/iot_hardware/peripheral/interfaces/kits",
    ]
}

修改**applications/sample/wifi-iot/app/BUILD.gn**文件，内容如下所示：

```
import("//build/lite/config/component/lite_component.gni")

lite_component("app") {
    features = [
        "hello:hello"
    ]
}
```

## 创建新发行版

创建一个新的发行版继承自本发行版，并执行发行命名

```
hpm init -t dist
hpm i @hihope/neptune_iot
hpm dist
```


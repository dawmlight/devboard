# 开发板名称：
Pegasus智能家居开发套件



#### 开发板描述：
Pegasus智能家居开发套件是江苏润和软件股份有限公司于2020年9月推出的OpenHarmony系列开发板之一，支持OpenHarmony 1.1.0 LTS开源版本。



##### 关键词: 

Wi-Fi IoT，Hi3861V100，智能家居，分布式能力

发行版@ohos/hispark_pegasus 版本1.0.4 发布于2021-04-08 09:53:07



## MCU/处理器

1.内部集成高性能32bit微处理器、硬件安全引擎以及丰富的外设接口
2.支持20MHz标准带宽和5MHz/10MHz窄带宽，提供最大72.2Mbit/s物理层速率
3.集成IEEE 802.11b/g/n基带和RF电路
4.Wi-Fi基带支持正交频分复用（OFDM）



## 开发板介绍

### 开发板概述

Pegasus智能家居开发套件基于海思Hi3861V100芯片设计，支持OpenHarmony，包含主板、通用底板、显示板、NFC板、智能红绿灯板、智能炫彩灯板、环境监测板、JTAG接口板；丰富的功能单板同时搭配扩展板，可输出多种外设控制信号，方便扩展更多传感器；NFC扩展板实现手机和单板互联 “碰一碰”；OpenOCD JTAG调试工具方便开发者快速调试。

Pegasus智能家居开发套件技术参数如下：

![智能家居套件产品参数](C:\Users\jz\Desktop\产品参数\产品参数\智能家居套件产品参数.png)

### 开发板功能

通过模块化的WLAN模组，适用于联接类模组设备，为各类IoT设备提供连接能力。



## 开发板详情

一、主板

主板是一片大约2cm*5cm大小、装载Hi3861V00 WLAN模组的开发板， Hi3861V100 WLAN模组是一款高度集成的2.4GHz WLAN SoC芯片，集成IEEE 802.11b/g/n基带和RF（Radio Frequency）电路。

该主板支持 OpenHarmony，并配套提供开放、易用的开发和调试运行环境。

![主板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\主板.png)



二、通用底板

WLAN模组主板卡槽：该卡槽位置插入主板。

NFC排线接口：通过NFC排线链接到NFC板上。

卡槽①：该位置只能插入显示板。

卡槽②：该位置可以插入智能红绿灯板、智能炫彩灯板、环境监测板。

底板供电电源切换开关：用于切换底板的供电来源；向上拨，表示使用主板电池电源给底板(以及扩展板)供电；向下拨，表示使用底板电池电源给底板（以及扩展板）供电。

电池接口：底板的电源输入口，可以接锂电池或者干电池。

底板5V电源切换开关：用于切换外设5V供电来源，跳冒接左边为电池给外设的5V电源供电；跳冒接右边为主板Type-C接口的5V给外设的5V电源进行供电。

JTAG接口：可以接入J-Link调试器，进行下载或者调试；也可以接入HiSpark_USB_JTAG板，使用OpenOCD进行下载或者调试。

![通用底板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\通用底板.png)



三、显示板

IIC接口OLED显示屏：0.96寸，IIC接口，12864分辨率，驱动芯片SSD1306。

用户按键1：通过底板连接到主板的GPIO05管脚；并使用GPIO05的复用功能ADC2进行AD采样，判断按键1的状态；按键1电压=3.3V2kΩ/6.7kΩ =0.985V。

用户按键2：通过底板连接到主板的GPIO05管脚；并使用GPIO05的复用功能ADC2进行AD采样，判断按键1的状态；按键2电压=3.3V1kΩ/6.7kΩ =0.493V。

备注：由于主板的用户按键同样连接在GPIO05关键，按照原理图，当按键按下，GPIO05管脚直接接到GND，此时，ADC2采样电压为0V，则表示为主板的用户按键有效。

![显示板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\显示板.png)



四、NFC板

NFC板载PCB线圈：使用印制电路板的方式设计的NFC天线线圈。

CSN/IRQ_N连接拨码开关：CSN接触端电源开关使能信号（低有效）；IRQ_N中断信号输出（低有效，开漏），AFE 透传模式下输出解调的数据；可选信号，在不使用的情况下，为了不影响NFC的工作，以及其他外设的工厂，拨码开关为断开状态。

NFC板排座：通过此排座可以直接将NFC板插入到底板的NFC排针接口处。

NFC排线插座：使用NFC排线，通过此插座将NFC板连接到底板的NFC插座接口处。

NFC芯片：FM11NC08I 符合 ISO/IEC14443－A 协议的 NFC 通道芯片，可完成I2C 接口和NFC 非接触接口之间的数据交互。

![NFC板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\NFC板.png)

五、智能红绿灯板

红色LED：通过底板连接到主板的GPIO10管脚。

黄色LED：通过底板连接到主板的GPIO14管脚。

绿色LED：通过底板连接到主板的GPIO11管脚。

蜂鸣器：通过底板连接到主板的GPIO09管脚。
（蜂鸣器的谐振频率为：2.7kHz。）

按键：通过底板连接到主板的GPIO08管脚。

（备注：因为GPIO08不具备ADC复用功能；所以，此按键只能通过编程识别IO口的高低电平状态，来判断按键是否按下，不同于显示板和主板中的按键可以通过AD采样值来判断按键状态。）

![智能红绿灯板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\智能红绿灯板.png)



六、智能炫彩灯板

三色LED：

红色LED通过底板连接到主板的GPIO10管脚。

蓝色LED通过底板连接到主板的GPIO14管脚。

绿色LED通过底板连接到主板的GPIO11管脚。

光敏电阻：通过底板连接到主板的GPIO09管脚（当有光照条件下，GPIO09 输入为低电平；当无光照情况下，GPIO09 输入为 高电平）

人体红外传感器：通过底板连接到主板的GPIO07管脚（当传感器检测到有人的时候，GPIO07 输入为高电平，否则为低电平。）

![智能炫彩灯板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\智能炫彩灯板.png)



七、环境监测板

温湿度传感器：AHT20数字输出，IIC接口。

蜂鸣器：通过底板连接到主板的GPIO09管脚（蜂鸣器的谐振频率为2.7kHz。）

可燃气体传感器：MQ-2 气体传感器使用气敏材料是在清洁空气中电导率较低的二氧化锡(SnO2)。当传感器所处环境中存在可燃气体时，传感器的电导率随空气中可燃气体浓度的增加而增大。使用简单的电路即可将电导率的变化转换为与该气体浓度相对应的输出信号；对丙烷、烟雾的灵敏度高，对天然气和其它可燃蒸气的检测也很理想。

![环境监测板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\环境监测板.png)





八、JTAG接口板

JTAG 接口排座：通过此排座，把JTAG接口板插入到底板中，使得使用的下载器可以通过接口板和底板的转接，与主板成功连接起来，从而进行软件的下载或者是在线调试。

调试器接口插座：此插座可以外接J-Link调试器，或者HiSpark_USB_JTAG 板（OpenOCD）对软件进行下载，已经程序的在线调测。



![JTAG接口板](C:\Users\jz\Desktop\OpenHarmony\OH官网润和开发板信息\OH官网润和开发板信息\OH官网润和开发板信息\Pegasus物联网开发套件信息\Pegasus物联网开发套件信息\img\JTAG接口板.png)



## 应用案例场景

### 开发板应用场景

Pegasus智能家居开发套件可广泛应用于常电智能家居，如白电、小家电、电工类。



### 上手指南

#### 环境搭建

1.首先根据官方网站安装IDE环境：Visual Studio Code、安装Python、安装Node.js、安装hpm、安装DevEco Device Tool插件

2.然后安装Windows编译环境：hcc_riscv32_win、ninja、gn、git

3.最后下载源码创建工程

#### 烧录步骤

1.首先在IDE 配置少些串口、烧写工具以及少些文件等

2.然后在IDE 中点击ProjectTask中upload即可实现烧录

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
hpm i @bearpi/bearpi_hm_nano
hpm dist
```


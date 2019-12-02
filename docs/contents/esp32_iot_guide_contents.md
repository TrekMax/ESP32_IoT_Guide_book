
## [前言](#前言)


<p align="left">
&nbsp;&nbsp;&nbsp;&nbsp;这篇文章是 "<b>ESP32</b> 开发指南(非乐鑫官方)" 教程的总纲；<br>
对于很多从事嵌入式开发的朋友应该都对 <b>ESP8266</b> 非常熟悉了！在 ESP8266 大热之后，乐鑫继而在 2015 年推出功能强劲的升级版 WIFI SOC: <b>ESP32</b>;<br>
&nbsp;&nbsp;&nbsp;&nbsp;然而我在学习/开发 ESP32 过程中却遇到很多坑，网上的资料现在零零碎碎的，故而写下本系列文章，希望能对在学习/开发 ESP32 踩坑中的你，能有少许帮助，谢谢！
</p>
<p align="right"><del>—— 码于 三月三号 二零一九年</del></p>

**备注:**

> 本系列文章基于 [**Espressif esp-idf**](https://github.com/espressif/esp-idf) Realse V4.x 版本
>
> 核心开发板 by [安信可 Ai-thinker](https://www.ai-thinker.com/home)@[NodeMCU-32S](https://www.ai-thinker.com/product/esp32)
>
> <img src="../_static/contents/esp32_nodemcu-32s_01.png" width=400  >

## 一、关于 ESP32

### 摘要

&nbsp;&nbsp;&nbsp;&nbsp;**ESP32** 是今年科创板上的新星公司 —— 乐鑫信息科技有限公司于 2015 年推出的 WIIF SOC;**ESP32** 芯片集成 801.11b/g/n/i **WIFI** 和 **Bluetooth 4.2** RF,并搭载两个 32位 Tensilica LX6 MCU,最高主频可达 **600DMIPS**,可直接传输音频流,视频流等,功能非常之强劲.

<img src="../_static/contents/esp32_soc_01.png" align=center width=800 alt="ESP32">

### ESP32 SOC 片上资源

<table style="border-collapse: collapse; min-width: 100%;" width="900px">
    <colgroup>
        <col style="width: 200px;">
        </col>
        <col style="width: 200px;">
        </col>
        <col style="width: 480px;">
        </col>
    </colgroup>
    <tbody>
        <tr>
            <td colspan="3"
                style="background-color: rgb(0, 168, 45); width: 879px; padding: 8px; border: 1px solid;">
                <div><span style="color: rgb(255, 255, 255);">ESP32 基本参数</span></div>
            </td>
        </tr>
        <tr>
            <td
                style="background-color: rgb(0, 168, 45); width: 201px; padding: 8px; border: 1px solid;">
                <div><span style="color: rgb(255, 255, 255);">类型</span></div>
            </td>
            <td
                style="background-color: rgb(0, 168, 45); width: 200px; padding: 8px; border: 1px solid;">
                <div><span style="color: rgb(255, 255, 255);">项目</span></div>
            </td>
            <td
                style="background-color: rgb(0, 168, 45); width: 480px; padding: 8px; border: 1px solid;">
                <div><span style="color: rgb(255, 255, 255);">规格</span></div>
            </td>
        </tr>
        <tr>
            <td rowspan="4" style="width: 200px; padding: 8px; border: 1px solid;">
                <div>CPU SOC</div>
            </td>
            <td style="width: 200px; padding: 8px; border: 1px solid;">
                <div>CPU</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>ESP32, 内置两个低功耗 Xtensa® 32-bit LX6 MCU(80Mhz/160Mhz/240Mhz)
                <br/>计算能力高达 650 DMIPS
                <br/>一个超低功耗协处理器 ULP
                </div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>ROM</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>448 KB 的 ROM</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>SRAM</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>用于数据和指令存储的 520 KB 片上 SRAM</div>
                <div>RTC 快速存储器，为 8 KB 的 SRAM</div>
                <div>RTC 慢速存储器，为 8 KB 的 SRAM</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>eFuse 安全加密</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>1 Kbit 的 eFuse</div>
            </td>
        </tr>
        <tr>
            <td rowspan="2" style="width: 201px; padding: 8px; border: 1px solid;">
                <div>Wi-Fi</div>
            </td>
            <td style="width: 200px; padding: 8px; border: 1px solid;">
                <div>协议</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>802.11 b/g/n（802.11n，速度 150 Mbps）</div>
                <div>A-MPDU 和 A-MSDU 聚合，支持 0.4 µs 保护间隔</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>频率范围</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>2.4 GHz ~ 2.5 GHz</div>
            </td>
        </tr>
        <tr>
            <td rowspan="3" style="width: 201px; padding: 8px; border: 1px solid;">
                <div>蓝牙</div>
            </td>
            <td style="width: 200px; padding: 8px; border: 1px solid;">
                <div>协议</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>符合<span style="color: rgb(45, 79, 201);">蓝牙 v4.2 BR</span>/EDR 和 BLE 标准</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>射频</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>具有–97 dBm 灵敏度的 NZIF 接收器</div>
                <div>Class-1, Class-2 和 Class-3 发射器</div>
                <div>AFH</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>音频</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>CVSD 和 SBC 音频</div>
            </td>
        </tr>
        <tr>
            <td rowspan="5" style="width: 201px; padding: 8px; border: 1px solid;">
                <div>硬件</div>
            </td>
            <td style="width: 200px; padding: 8px; border: 1px solid;">
                <div>模组接口：</div>
                <div><span style="font-size: 16px;"><span
                            style="font-size: 16px; color: rgb(0, 0, 0); font-family: 微软雅黑;">34 个 GPIO
                            口</span></span></div>
                <div><span style="color: rgb(227, 0, 0);">模组 GPIO6 至 GPIO11 用于连接模组上 集成的 SPI
                        flash/PSRAM，不建议用于其他功能</span></div>
                <div><span style="color: rgb(227, 0, 0);">（可用 28个）</span></div>
                <div><br /></div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>• 34 个 GPIO 口 </div>
                <div>• 12-bit SAR ADC，多达 18 个通道 </div>
                <div>• 2 个 8-bit D/A 转换器</div>
                <div>• 10 个触摸传感器</div>
                <div>• 4 个 SPI <span style="color: rgb(45, 79, 201);">[可重映射]</span></div>
                <div>• 2 个 I²S<span style="color: rgb(45, 79, 201);"> [可重映射]</span></div>
                <div>• 2 个 I²C <span style="color: rgb(45, 79, 201);">[可重映射]</span></div>
                <div>• 3 个 UART <span style="color: rgb(45, 79, 201);">[可重映射]</span></div>
                <div>• 1 个 Host SD/eMMC/SDIO </div>
                <div>• 1 个 Slave SDIO/SPI </div>
                <div>• 带有专用 DMA 的以太网 MAC 接口，支持 IEEE 1588 </div>
                <div>• CAN2.0 • IR (TX/RX) </div>
                <div>• 电机 PWM </div>
                <div>• LED PWM，多达 16 个通道 </div>
                <div>• 霍尔传感器</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>片上传感器</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>霍尔传感器</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>工作电压/供电电压</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>2.7 V ~ 3.6 V</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>最小供电电流</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>500 mA</div>
            </td>
        </tr>
        <tr>
            <td style="border: 1px solid; width: 200px; padding: 8px;">
                <div>建议工作温度范围</div>
            </td>
            <td style="width: 480px; padding: 8px; border: 1px solid;">
                <div>–40 °C ~ 65 °C</div>
            </td>
        </tr>
    </tbody>
</table>


> more...

### 开发框架/平台资源

| 开发框架/解决方案 | 🔗链接 | 说明 |
|---|---|---|
| ESP-IDF | espressif@[esp-idf](https://github.com/espressif/esp-idf) | IoT 开发框架 |
| ESP-ADF | espressif@[esp-adf](https://github.com/espressif/esp-adf) | 音频开发框架 |
| ESP-MDF | espressif@[esp-mdf](https://github.com/espressif/esp-mdf) | WIFI-MESH 开发框架 |
| esp-iot-stution |espressif@[esp-iot-stution](https://github.com/espressif/esp-iot-solution) | IoT 解决方案 |
| esp-jumpstart |espressif@[esp-jumpstart](https://github.com/espressif/esp-jumpstart) | 快速上手示例 |

> more ...


### ESP32 开发教程

乐鑫官方编程指南: [ESP32-IDF 编程指南](https://docs.espressif.com/projects/esp-idf/zh_CN/latest/get-started/index.html)

## 二、ESP32 开发环境搭建&开发框架指南

### 简介

&nbsp;&nbsp;&nbsp;&nbsp;由于 ESP8266/ESP32 是乐鑫科技基于 Xtensa 内核定制的 WIFI SOC, 非 STM32,MM32 等主流 Cortex-M 内核架构，所以无法使用 MDK(Keil)/IAR 等主流 MCU 开发环境;
&nbsp;&nbsp;&nbsp;&nbsp;而乐鑫主推的官方开发环境为 Linux, 但国内大部分嵌入式/单片机开发者都是在 Windows 上进行开发,所以我们下面的将在 Windows 上搭建我们的开发环境.

### ESP32 开发环境搭建

**开发环境介绍:**

&nbsp;&nbsp;&nbsp;&nbsp;这里根据乐鑫官方的教程，以实际的开发情况，我们可以有以下几种开发环境供我们选择(GNU Make 逐渐弃用,换用 CMake):

| 开发环境     | 说明 | 文章 | 备注 |
| --- | --- | --- | --- |
| WSL(Linux)+ Make + VS Code | WSL(Linux) + VS Code 搭建 ESP32 开发环境 | 该环境搭建分成两部分,<br/>第一部分是安装配置 WSL: [《WSL 简明使用教程 — 安装&配置》](./Development_environment/dev_env_wsl_install.md)<br/> 第二部分是在 WSL +VS Code 配置 ESP32 开发环境:[《WSL + VS Code 搭建 ESP32 开发环境》](./Development_environment/dev_env_wsl_install_2.md) | 更新中 |
| CMake(Windows) + VS Code | 使用 ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境 | [《ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境》](./Development_environment/dev_env_esp-tools_install.md) | 更新中 |
| MSYS2(Windows)  + VS Code | Win 7/8/10 + Msys2 + VS Code 搭建 ESP32 开发环境<br/> (编译工程过慢,且易出错,官方弃用中) | - | 待更新 |
| - | - | - | - |

#### WSL(Linux) + VS Code 搭建 ESP32 开发环境

**WSL** 即  **”Windows Subsystem for Linux”**  的缩写，顾名思义，**WSL** 就是 Windows 系统下的 Linux 子系统，
> **WSL** 作为 **Windows** 的组件搭载在 **Windows 10** 周年更新(**1607**) 之后的系统中,所以下面文章仅适用于 Windows 10 (**1607**) 之后的系统

该环境搭建分成两部分:

第一部分是 安装配置 WSL，第二二部分是在 WSL +VS Code 配置 ESP32 开发环境，所以分成两篇文章:

> 由于 WSL 是 Linux 系统, 故与 Linux 下搭建 ESP32 方法相同
> Linux (WSL)系统使用 Ubuntu 18 LTS

[一、《WSL 简明使用教程 — 安装&配置》](./Development_environment/dev_env_wsl_install.md)

[二、《WSL + VS Code 搭建 ESP32 开发环境》](./Development_environment/dev_env_wsl_install_2.md)

#### 使用 ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境

由于大部分嵌入式/MCU 开发工程师都是在 Windows 进行开发的,所以乐鑫推出了适用于 Windows 上搭建 ESP32 开发环境的安装器 **ESP-IDF 工具安装器**`(ESP-IDF-tools-setup)`

下载地址:
[https://dl.espressif.com/dl/esp-idf-tools-setup-2.0.exe](https://dl.espressif.com/dl/esp-idf-tools-setup-2.0.exe)

我们可以使用 ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境 来快速搭建 ESP32 开发环境

[《ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境》](./Development_environment/dev_env_esp-tools_install.md)


#### Msys2(Windows) + VS Code 搭建 ESP32 开发环境

- 暂不更新
(编译工程过慢,且易出错,官方弃用中)

### ESP32 IOT 开发框架与编译系统

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| D000 | [D000.make]() | [ESP32 构建系统之 make 指令 && makefile]() | None.|
| D001 | [D001.kconfig]() | [ESP32 构建系统之 Kconfig]() | None.|
| D002 | [D002.menuconfig]() | [menuconfig]() | None.|

> more ...

## 三、ESP32 基础开发指南

### ESP32 外设例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| P001 | [P001.gpio_output_led]() | [GPIO 点亮LED ]() | None.|
| P0** | [*](./) | [P0**_*](./) | * |

> more...

### ESP32 WIFI & INTERNET 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| W000 | [W000.SoftAP+STA]() | [ESP32 Soft+AP&STA 模式使用]() | None.|
| W0** | [*](./) | [W0**_*](./) | * |

> more...

### ESP32 BLE 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| B0** | [*](./) | [B0**_*](./) | * |

> soon in...

### ESP32 FreeRTOS 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| F001 | [ESP32_FreeRTOS_任务管理](./) | * | * |
| F002 | [ESP32_FreeRTOS_软件定时器](./) | * | * |
| F003 | [ESP32_FreeRTOS_事件标志组](./) | * | * |
| F004 | [ESP32_FreeRTOS_信号量-二值信号量](./) | * | * |
| F005 | [ESP32_FreeRTOS_信号量-优先级翻转](./) | * | * |
| F006 | [ESP32_FreeRTOS_信号量-互斥信号量](./) | * | * |
| F007 | [ESP32_FreeRTOS_消息队列](./) | * | * |
| F008 | [ESP32_FreeRTOS_任务通知](./) | * | * |
| F0** | [*](./) | * | * |

> more...

## 四、ESP32 进阶开发指南

### ESP32 SIG MESH 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| MB0** | [*](./) | * | * |

> soon in...

### ESP32 ADF 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| A0** | [*](./) | * | * |

> soon in...

### ESP32 MDF 例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| MW0** | [*](./) | * | * |

> soon in...

## 五、ESP32 高级开发指南


### ESP32 应用例程

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| C0** | [*](./) | * | * |

> soon in...

## 六、ESP32 Geek 开发指南

### ESP32 MicroPython

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| PY0** | [*](./) | * | * |

> soon in...

### ESP32 Ardunio

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| AD0** | [*](./) | * | * |

> soon in...

### ESP32 Javascript

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| JS0** | [*](./) | * | * |

> soon in...

### ESP32 Geek 设计

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| G0** | [*](./) | * | * |

> soon in...

### ESP32 HackCube 设计

| 序号 | 笔记 & 教程 | 工程源码 | 备注 |
| --- | --- | --- | --- |
| H0** | [*](./) | * | * |

> soon in...

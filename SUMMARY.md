# Summary

* [简介](README.md)

* [ESP32 IoT 开发指南 总纲](./docs/contents/esp32_iot_guide_contents.md)

* [一、ESP32 开发环境搭建]()

    * [WSL 简明使用教程 — 安装&配置](./docs/Development_environment/dev_env_wsl_install.md)
    * [WSL + VS Code 搭建 ESP32 开发环境](./docs/Development_environment/dev_env_wsl_install_2.md)

    * [ESP-IDF 安装器 + VS Code 搭建 ESP32 开发环境](./docs/Development_environment/dev_env_esp-tools_install.md)

* [二、ESP32 IoT 开发框架与编译系统]()

    * [ESP-IDF SDK 框架解析]()
        * [ESP-IDF SDK 结构 - 组件(components)](./README.md)
        * [ESP-IDF SDK 结构 - Kconfig(components)](./README.md)

    * [ESP-IDF 构建系统](./README.md)
        * [GUN Make 构建系统]()
        * [CMake 构建系统]()

* [三、ESP32 基础开发指南]()

    * [ESP32 常用外设开发]()
        * [ESP32 GPIO 操作]()
        * [ESP32 UART 操作]()
        * [ESP32 IIC 操作]()
        * [ESP32 SPI 操作]()
        * [ESP32 SDIO 操作]()

    * [ ESP32 WIFI & Internet 开发]()
        * [ESP32 连接 WIFI AP(Station 模式)]()
        * [ESP32 创建 Soft AP(Soft AP 模式)]()
        * [ESP32 Station + Soft AP共存]()

    * [ ESP32 BLE 例程](./README.md)
        * [Bluetooth &&BLE 基础知识扫盲](./README.md)
            * [BLE 协议栈 - 物理层(Physical Layout)](./README.md)
            * [BLE 协议栈 - 链路层(Link Layout)](./README.md)
            * [BLE 协议栈 - HCI(Host Controller Interface)](./README.md)
            * [BLE 协议栈 - L2CAP(Logical Link Control and Adaptation Protocol)](./README.md)
            * [BLE 协议栈 - ATT(Attribute Protocol)](./README.md)
            * [BLE 协议栈 - GATT(General Agreement on Tariffs and Trade)](./README.md)
            * [BLE 协议栈 - GAP(Generic Access Profile)](./README.md)

* [四、ESP32 进阶开发指南]()

    * [ESP32_FreeRTOS 内核开发](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_任务管理](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_软件定时器](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_事件标志组](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_信号量-二值信号量](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_信号量-优先级翻转](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_信号量-互斥信号量](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_消息队列](./docs/Guide_freertos/esp32_freertos.md)
        * [ESP32_FreeRTOS_任务通知](./docs/Guide_freertos/esp32_freertos.md)

    * [ESP32 功能组件开发]()
        * [ESP32 控制台组件 - Console]()
        * [ESP32 文本处理组件 - cJSON]()

    * [ESP32 ESP-IDF 协议开发](./README.md)
        * [MQTT 协议开发](./README.md)
            * [MQTT 基础知识](./README.md)
        * [HTTP/HTTPS 协议开发](./README.md)
            * [HTTP 基础知识 - TCP 连接三次握手,断开四次握手](./README.md)
            * [HTTP 基础知识 - GET/POST](./README.md)
        * [Websocket 协议开发](./README.md)

    * [ESP32 对接云端开发](./README.md)
        * [对接 阿里智能云平台](./README.md)
        * [对接 腾讯 IoT Explorer](./README.md)
        * [对接 华为 HiLink](./README.md)
        * [对接 京东小京鱼](./README.md)
        * [对接 百度天工(百度物平台)](./README.md)
        * [对接 Google IoT Core](./README.md)
        * [对接 AWS-IoT](./README.md)
        * [对接 AZURE](./README.md)

    * [ESP32 ESP-IDF 框架/组件分析](./README.md)
        * [ESP32 ESP-IDF 框架/组件分析](./README.md)
        * [ESP32 ESP-IDF EVENT 框架分析](./README.md)


    * [ESP32 SIG MESH 例程](./README.md)
        * [SIG Mesh 基础知识扫盲](./README.md)
            * [SIG Mesh 简介](./README.md)
            * [SIG Mesh 各个角色的功能简介](./README.md)
            * [SIG Mesh 协议层次功能简介](./README.md)
            * [什么是 Element 和 Model](./README.md)

        * [SIG Mesh 应用开发指南-基础篇](./README.md)
        * [SIG Mesh 应用开发指南-进阶篇](./README.md)
        * [SIG Mesh 应用开发指南-实战篇](./README.md)
        * [SIG Mesh 扩展知识-安全篇](./README.md)

    * [ESP32 ADF 例程(待更新)]()
    * [ESP32 MDF 例程(待更新)]()

* [五、ESP32 高级开发指南(待更新)]()
    * [ESP32 应用例程(待更新)]()

* [六、AURORA 蓝牙网关(更新中)]()
    * [AURORA ESP32 SDK 简介](./docs/aurora_ble_gateway/README.md)
    * [AURORA ESP32 SDK 框架/组件分析](./docs/aurora_ble_gateway/README.md)

* [七、开发工具及使用技巧](./README.md)
    * [开发工具 - VS Code]()
    * [开发工具 - 常用 shell 命令/脚本](./docs/utils_tools/dev_tools_shell.md)
    * [开发工具 - make 命令/脚本]()
    * [开发工具 - git 命令/脚本]()
    * [开发工具 - python 命令/脚本]()
    * [开发工具 - Kconfig 使用]()
    * [开发工具 - Postman/PostWoman 使用]()
    * [开发调试/编辑软件/工具 - 推荐]()

* [结束]()
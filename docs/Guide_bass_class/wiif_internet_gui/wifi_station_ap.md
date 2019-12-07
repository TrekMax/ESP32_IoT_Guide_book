# ESP32 WIFI STATION/AP 使用流程

## ESP32 WIFI 接口使用流程

`STATION` && `AP` && `STATION + AP` 模式

STATION 模式

- 初始化 TCP/IP Adapter (LWIP 协议适配器)

```c
tcipip_adapter_init();
```

- 配置 WIFI 默认参数

- 注册 WIFI 事件

- 注册用户事件回调处理函数

    WIFI_EVENT

    IP_EVENT

    ETH_EVENT

- 启动 WIFI

# 无线读卡器

一款基于ESP12模组实现的无线式SD、TF卡读卡器，只需将已插入待读取存储卡的本设备插入任何可供DC5V的USB端口即可，它将创建一个架设在WiFi上的FTP服务器，我们可以通过其进行对存储卡的读写操作。源工程来自 //www.hackster.io/Neutrino-1 的 //www.hackster.io/Neutrino-1/wireless-sd-card-reader-esp8266-de7f07 ，本项目仅依照源工程文章描述通过LCEDA绘制了合适的PCB原理图与电路。

![打样图](https://github.com/Giftia/Wireless_SD/blob/master/PCB.jpg)

### 开始

下载zip包，解压并重命名文件夹为 Wireless_SD，即去掉 '-master' 字符串，使用Arduino IDE(在1.8.12上测试通过)打开目录下的 Wireless_SD.ino，相关依赖文件会一并打开。因体积和成本原因没有外围烧录电路，所以需要固件烧录完毕再行焊接。参考下图接线图，使用任意USB-TTL烧录器连接ESP12模组，点击Arduino IDE的上传按钮烧录至ESP12模组，再将ESP12模组焊接至PCB上。

![USB-TTL接线图](http://wiki.ai-thinker.com/_media/esp_download/downloadfirmware_hardware.png)

### 开发板管理器(Arduino的迷惑翻译)

* [ESP-Core](https://github.com/esp8266/Arduino) - by Ivan Grokhotkov

### 使用方法

将SD/TF存储卡插入卡槽，并插入任意提供DC5V的USB端口上电，接下来请按照如下步骤进行文件传输：
```
-> 连接一个SSID为 'SDcard Reader' 的WiFi，密码是 'OSHWHubNB'，有些系统会弹窗提示该连接无网络，是正常现象，请勿断开连接。

-> 打开FTP客户端，安卓端建议：AndFTP、ES文件浏览器，Windows端建议：WinScp、FileZilla Client。

-> 配置FTP的主机名为 '192.168.12.7'，端口为 21。

-> 用户名与密码均为 'esp8266'。

-> 连接即可。
```

## 开源协议

GPL 3.0

## 致谢

* 来自 [Neutrino-1](https://github.com/Neutrino-1) 的开源项目。
* [David Paiva](https://github.com/nailbuster) 为 ESP8266/ESP32 移植的 Arduino FTP 库。

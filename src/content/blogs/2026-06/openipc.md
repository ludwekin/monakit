第一次通电,板子会启动 U-Boot → Linux 系统。

通过 RJ45 网口 请求 IP（DHCP 模式）,如果你的路由器/电脑直连，会自动获取 IP（常见如 192.168.x.x）。


刷好自定义固件后，插上 网线（RJ45） + 电源。

用电脑扫描网络，找到板子的 IP（或者用 ARP 扫描工具）。

浏览器访问 http://相机IP 查看 Web 界面。

SH 登录（root + 你设置的密码）：检查日志：logread 或 dmesg | grep imx307
编辑 Divinus 配置：vi /etc/divinus.yaml
重启 streamer：/etc/init.d/divinus restart（或对应命令）

用 VLC 测试 RTSP 流：rtsp://root:密码@IP/stream=0







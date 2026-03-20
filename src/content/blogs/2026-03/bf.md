移植bf的滤波器/算法是很有必要的。

比如dshot通信算法。

比如rpm滤波。

多动态陷波滤波器 很有用。电机噪声是个至关紧要的大问题。

PID控制器变体 ，包括前馈增强和Super Expo。算法通过棒量输入修改P/D项增益，实现非线性响应。

移植 PID在高动态系统中的扩展算法。 对机器人的 快速响应 有前沿的引导作用。



bf固件可以实现飞控的串口快速通讯功能。

对于无 USB VCP 的板子，可把某个 UART 配置为 MSP，然后通过 USB‑TTL 接到该 UART，仍可用 App 的 CLI 或串口终端进入。

USB VCP 是基于 USB CDC 类（Communication Device Class）中的 CDC-ACM 子类（Abstract Control Model）实现的。

现在很多单片机/开发板已经没有物理串口芯片了，或者想省掉一个转接芯片（比如FT232、CH340），于是就用设备自身的USB接口直接模拟出一个串口给电脑看。








AIO板（FC+ESC+VTX一体化） 的核心优势就是单机更便宜、更小、更轻（省掉堆叠连接器、线材、螺丝），但最大的挑战就是电机/ESC噪声（电气EMI + 切换噪声） 会直接影响MCU和IMU（陀螺仪/加速度计），导致黑匣子噪声大、滤波难调、飞行抖动或飞控失控。好消息是：现代AIO（尤其是1S Whoop用F411/F435/G473）已经把隔离做到极致，靠布局+电源+接地+滤波四重防护，而不是靠“魔法”。AIO是怎么做隔离的？（实战核心技术）电源域完全隔离（最重要！）ESC走原始电池电压（1S就是3.0~4.2V直供MOSFET），MCU+IMU走独立干净电源。



常用方案：专用LDO（或小Buck）给3.3V/5V轨（IMU专用LDO最好，噪声<50μV）。
Betaflight官方推荐：IMU用独立LDO + 两个20nF输出电容。
1S AIO里常见：电池输入先接大电容 → LDO → 再接IMU专用滤波。

结果：ESC切换产生的纹波几乎传不到陀螺仪供电。

接地“单点连接”（Split Ground / Star Ground）最经典做法：ESC大电流地平面 和 FC敏感地平面只在电池输入口附近单点连接（通常用一个焊盘或粗过孔）。
高电流回流路径不会经过IMU区域，避免“地弹”（ground bounce）。
多层板（4层推荐）：Layer 2/3做完整GND平面 + 缝合过孔（via stitching，每5-10mm一个），把多层地“缝”成低阻抗整体。
这就是为什么很多AIO飞起来比老堆叠还干净。

布局物理分区（Component Placement）IMU放板子中心或远离ESC区（离电机焊盘/MOSFET至少10-15mm）。
ESC MOSFET、电流采样电阻、电感放在板子边缘或背面。
电源电感/开关器件放在IMU对面那一侧（磁场不会耦合进陀螺）。
电机相线走底层，信号线走顶层，中间GND层做屏蔽。
模拟区（IMU） / 数字区（MCU） / 功率区（ESC）三区分离，像微型四轴PCB设计里说的“远离电机驱动”。

滤波与去耦（Filtering）每个IC电源脚旁100nF贴片电容（距离<3mm）。
电源入口放10-100μF钽电容或电解 + 陶瓷组合。
IMU供电线加铁氧体磁珠（ferrite bead） 或 LC滤波。
ADC（VBAT/CURR）全部加100nF旁路。


1S板子空间小，但高手都会在设计时预留“滤波焊盘”方便后期加容。

额外屏蔽（可选但有效）IMU周围做接地铜围栏（via fence）。
高端AIO会给FC区加金属屏蔽罩（shield can），完全挡住ESC开关噪声。
4层板以上用信号-地-电源-信号叠层，天然屏蔽。

1S Whoop AIO特别提醒（你自研最关心的）1S电流小、电压低，噪声其实比4S/6S好控制，但陀螺还是怕（尤其是BMI270/ICM42688）。
常见问题：电机高速时黑匣子出现“电噪声峰值” → 加2-3个100μF低ESR电容在电池焊盘就能解决80%。
自研时推荐4层板（Layer 1信号 / Layer 2 GND / Layer 3 POWER+GND split / Layer 4信号+ESC）。
层压顺序：Top信号 → GND → Power/GND split → Bottom（ESC相线）。
参考Betaflight官方设计指南 + PCBSync AIO布局文章，基本不会踩坑。


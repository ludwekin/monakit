#elif defined(STM32F4)
  #define CPU_FREQ            168000000    // 主频 = 168 MHz
  #define PERI1_FREQUENCY     42000000     // APB1 总线频率 = 42 MHz
  #define PERI2_FREQUENCY     84000000     // APB2 总线频率 = 84 MHz
  #define TIMER_MULT_APB1     2            // APB1上的定时器时钟倍频系数 = 2
  #define TIMER_MULT_APB2     2            // APB2上的定时器时钟倍频系数 = 2

  
  
  12 MHz 在一些 RC 遥控器设计中挺流行，因为它对某些 UART 波特率（比如 FrSky 内部协议、串口调试）、定时器分频、USB 时钟（如果有）更容易整出整数倍。  


  
  以太网 PHY 需要 25 MHz MCO 输出。

  STM32F407 不是“随便接什么晶振都行”，但在 4–26 MHz 这个窗口里，确实支持很多常见频率，你可以根据需求（USB、以太网、代码兼容、PLL 整数等）灵活选。



# Radiomaster Pocket 硬件规格与引脚清单

## 概览
- 目标口味：pocket（X7 家族）
- MCU：STM32F407xE（HSE=12MHz）
- 模块仓：NANO（小型）
- 显示：128x64 单色 LCD，SPI 驱动，竖向翻转显示
- 背光：TIM4 CH2 PWM（PD13）
- USB 名称：Radiomaster Pocket

## 电源与电池
- 电源按键：PD1（PWR_SWITCH_GPIO）
- 软开机输出：PD0（PWR_ON_GPIO）
- 电池采样：PC0，ADC1_IN10
- 电池分压：R1=499kΩ，R2=160kΩ，MOSFET 压降系数=25×10mV

## 状态 LED
- 绿：PE2
- 红：PE13
- 蓝：PA7
- 输出为置位点亮

## 显示与背光
- LCD 接口（SPI3）
  - MOSI：PC12
  - SCK：PC10
  - A0/DC：PC11
  - NCS：PA15
  - RST：PD12
- 背光 PWM：TIM4 CH2，PD13，GPIO AF2
- 显示方向：竖向翻转（LCD_VERTICAL_INVERT）

## 摇杆与旋钮（ADC）
- 摇杆（ADC1）
  - RV：PA0（IN0）
  - RH：PA1（IN1）
  - LV：PA2（IN2）
  - LH：PA3（IN3）
- 旋钮
  - P1：PB0（ADC1_IN8）
  - P2：无（Pocket 未定义 PA6）
- 电池：PC0（ADC1_IN10）
- 方向数组：{-1, 1, 1, -1, -1}

## 导航旋钮（Rotary Encoder）
- 引脚：A=PE9，B=PE10
- EXTI：LINE9/LINE10，优先级兼容 FreeRTOS
- 方向：反向（ROTARY_ENCODER_INVERTED）

## 面板按键
- PageUp：PD3
- PageDn：PD7
- Exit：PC5
- Enter：PA13
- Sys：PB4
- Model：PE11
- Tele：PD2

## 拨杆（Switches）
- SA：PC13（单引脚）
- SB：PE1（高）/ PE2（低）
- SC：PE0（低）/ PD11（高）
- SD：PE8（单引脚）
- SE：PE7（单引脚）
- 备注：Pocket 无 SWF/G/H/I/J

## 内置模块（默认 CRSF）
- 供电：PC4
- BootCmd：PB1（默认复位=0）
- 串口：USART1
  - TX：PB6
  - RX：PB7
  - TX DMA：DMA2 Stream7 Channel4
  - RX DMA：DMA2 Stream2 Channel4

## 外置模块（NANO 仓）
- 供电：PD8
- 串口：USART6
  - TX：PC6
  - RX：PC7
  - TX DMA：DMA2 Stream6 Channel5
  - RX DMA：DMA2 Stream1 Channel5
- 定时器：TIM8 CH1，GPIO AF3，DMA2 Stream1 Channel7

## 训练口（3.5mm）
- 输入：PC8（TIM3 CH3）
- 输出：PC9（TIM3 CH4）
- 检测：PA8（低为插入，带输入反转）

## I2C / EEPROM / 音量
- I2C1：SCL=PB8，SDA=PB9
- EEPROM：地址 0x51，写保护 PD10
- 软件音量关闭时使用 I2C 音量芯片（地址 0x2E）

## SD 卡（SPI2）
- CS：PB12
- SCK：PB13
- MISO：PB14
- MOSI：PB15
- 检测：PD9

## USB / 音频 / 震动
- USB：VBUS=PA9，DM=PA11，DP=PA12
- 音频输出：PA4（TIM6，DMA1 Stream5）
- 震动马达（Haptic）：PB3，TIM2 CH2 PWM



  elseif(PCBREV STREQUAL POCKET)
    set(DEFAULT_INTERNAL_MODULE CROSSFIRE CACHE STRING "Default internal module")
    set(INTERNAL_MODULE_SERIAL YES)
    set(MODULE_SIZE_SML YES)
    set(FLAVOUR pocket)
    set(CPU_TYPE_FULL STM32F407xE)
    set(ROTARY_ENCODER YES)
    set(USB_CHARGER YES)
    add_definitions(-DRADIO_POCKET)
    add_definitions(-DMANUFACTURER_RADIOMASTER)
    set(PXX2 ON)
    set(ENABLE_SERIAL_PASSTHROUGH ON CACHE BOOL "Enable serial passthrough")
    if (NOT BLUETOOTH)



该遥控器在固件配置中将“默认内置模块”设为 CROSSFIRE，并开启串口内置模块支持，这意味着电台与内置射频头通过 CRSF 串口协议交互： CMakeLists.txt:POCKET

电台并不固定 ExpressLRS 的具体版本，CRSF 协议栈由电台实现、ELRS 版本由内置模块的固件决定（常见为 ELRS 3.x，2.x 亦可）。只要模块端提供 CRSF TX 行为，电台即可兼容。

- 串口连接内置模块（CRSF）：USART1 TX PB6、RX PB7，已配置 DMA 传输通道。
- 模块供电控制：PC4 作为 INTMODULE_PWR_GPIO，用于开关模块电源。
- Boot/复位控制：PB1 作为 INTMODULE_BOOTCMD_GPIO（Pocket 默认复位态为 0），可用于进入模块引导模式或强制复位。

方案A：SWD 初次烧录（推荐）

- 接线：SWDIO=PA13、SWCLK=PA14、NRST 及 3V3/GND
- 工具：STM32CubeProgrammer 或 st-flash
- 步骤
  - 烧写引导程序：选择 bootloader.bin/hex，地址 0x08000000
  - 烧写主固件：选择 firmware.bin，地址 0x08008000
  - 断电重上电，进入系统；之后即可使用 SD 卡/USB 进行升级
方案B：DFU ROM 引导烧录

- 进入系统引导：将 BOOT0 拉高（接 3V3），复位后枚举为 DFU
- 工具：STM32CubeProgrammer（USB）或 dfu-util
- 步骤同 SWD：先写 0x08000000 的引导程序，再写 0x08008000 的主固件
后续升级方式

- SD 卡升级
  - 将 firmware.bin 拷贝到 SD 卡 FIRMWARE/ 目录
  - 进入引导菜单，选择写入（Pocket 的按键组合依赖 BOOTLOADER_KEYS，机型为 X7 家族，按键参考电台屏幕提示或厂商文档）
- Companion 升级
  - 通过 USB 与 PC 配合 Companion，将 firmware.bin 推送到电台并写入


cmake -DPCB=X7 -DPCBREV=POCKET -DTRANSLATIONS=EN -DRADIOMASTER_RELEASE=YES .

make firmware -j6

总体流程

- 配置阶段：cmake 读取源码树，根据你指定的 -D 变量选择机型分支、设定宏与编译选项，生成构建系统
- 编译阶段：make firmware 并行编译所需对象库与目标，链接生成固件 ELF，随后转换为 firmware.bin
- 产物位置：通常在构建目录的 arm-none-eabi/ 下生成 firmware.bin（本工程脚本就是从这个路径拷贝输出）

-j6 表示最多 6 个任务并行，CMake/Ninja/Make 根据依赖图并行编译位图、字体、板库、驱动、GUI 等


同一代码库面向几十款电台与多种 MCU（F2/F4/H7），用配置选项把“谁用哪些源文件、哪些宏、哪些外设映射”描述清楚，避免复制粘贴分叉

- 提供统一的 cmake 命令，让构建过程可重复、可脚本化，不用手改 makefile 或编译器参数


顶层构建脚本负责“通用规则与聚合”radio/src/CMakeLists.txt


怎么把edgetx的关于pocket遥控器代码的部分移植到stm32官方的cubeide工具里面二次修改开发？


  elseif(PCBREV STREQUAL POCKET)
    set(DEFAULT_INTERNAL_MODULE CROSSFIRE CACHE STRING "Default internal module")
    set(INTERNAL_MODULE_SERIAL YES)
    set(MODULE_SIZE_SML YES)
    set(FLAVOUR pocket)
    set(CPU_TYPE_FULL STM32F407xE)
    set(ROTARY_ENCODER YES)
    set(USB_CHARGER YES)
    add_definitions(-DRADIO_POCKET)
    add_definitions(-DMANUFACTURER_RADIOMASTER)
    set(PXX2 ON)
    set(ENABLE_SERIAL_PASSTHROUGH ON CACHE BOOL "Enable serial passthrough")
    if (NOT BLUETOOTH)
      set(AUX_SERIAL ON)
    endif()
  elseif(PCBREV STREQUAL T8)

  CubeIDE 外设与引脚配置清单

HSE=12MHz，PLL 配到 SYSCLK=168MHz；APB1=42MHz、APB2=84MHz；Timer 在 APB1/APB2 上乘2

摇杆：PA0/1/2/3 → ADC1_IN0/1/2/3

- 旋钮 P1：PB0 → ADC1_IN8；电池：PC0 → ADC1_IN10
- ADC DMA：DMA2 Stream4 Channel0；采样时间：28 cycles；方向数组：{-1, 1, 1, -1, -1}

初始化顺序与驱动骨架

- 典型顺序（CubeIDE 的 main 中组织）
  - 使能 SYSCFG/时钟、LL 或 HAL 初始化
  - delaysInit、timersInit（系统定时）
  - usbInit（如连接充电 LED 逻辑）
  - board_trainer_init
  - pwrInit（读取 PCBREV/上电流程）
  - boardInitModulePorts（模块仓 GPIO 方向）
  - keysInit、switchInit
  - rotaryEncoderInit（配置 EXTI 与定时器）
  - adcInit → getADC（做一次采样）
  - lcdInit（SPI3 与 DMA）、audioInit
  - rgbLedInit（如启用）
  - hapticInit
  - rtcInit（如启用）
  - backlightInit、lcdSetContrast
  - 参考流程： board.cpp:boardInit
- NVIC 与优先级建议
  - Telemetry EXTI（PD6）：优先级 0（软串口需要） hal.h: TELEMETRY_EXTI_PRIO
  - Rotary EXTI9_5/15_10：优先级 5
  - DMA/USART 中断优先级根据数据流量适度下调（例如 5–7），保障实时 EXTI
  - SysTick：FreeRTOS 情况下保持默认并遵循 FreeRTOS 要求



工程原生大量使用 LL（Low-Layer），CubeIDE 可选启用 LL 驱动，避免混用导致风格不一致



- Pocket 将 Enter 使用在 PA13，调试阶段不要重映射或在运行时禁用 SWD；必要时可暂不接 Enter 或用调试配置保留 SWD


电源控制：PC4/PD8 的模块电源脚要通过 MOSFET 受控，首次 bring-up 可直接常开以简化。


等等，为啥这个项目不像一般的stm32开发教程里面教的那样用cubemx+keil+hal库开发，而是自起门户用vscode?来开发？

Arm GNU + CMake 更适合跨平台开源协作与 CI/CD。

工程大量使用 LL（Low-Layer）与自定义驱动，而非 HAL 的“通用封装”，以减小体积、减轻抽象层的开销。在 targets/common/arm/stm32/* 里有针对性的驱动实现，方便做 DMA/EXTI/定时器优先级的精细调度。

相同代码库同时产出 bootloader 和 firmware 两个目标，并按屏幕分辨率切换位图/字体资源、按机型切换外设源码与宏。 板库与目标组织 。


stm32cubeide可以用ll来开发吗？和hal有什么区别？

STM32CubeIDE 当然可以用LL开发，而且现在用得非常方便。
大多数人最终会走到“关键外设用LL + 其他用HAL”这条路，既能快速开发，又能得到较好的性能和体积。

用stm32cubeide创建的新项目，目的是移植edgetx的一系列有用固件来给我的遥控器PCB实现功能，然后硬件的原理图就是pocket那一套。

完全可以用纯代码实现引脚配置，而不依赖 CubeMX 生成的代码。

f407比f405多的以太网有啥用？怎么开发？

难道f407不能实现usb phy吗？我看这好像是f405特有的功能。



补充，TM32 的命名规则（Part Number）是 ST 公司自己定义的一套体系，不同系列（如 F1、F4、H7、L4 等）在细节上会略有差异，但整体框架基本一致。

简记，引脚，flash，封装，温度。


怎么设计原理图，让我的PCB（stm32f407作为mcc）实现引出4根swd线的同时，又可以在不用swd的时候让引脚作为别的用处？

需要在原理图中添加可配置的隔离元件，如跳线（Jumper）、0 欧姆电阻（0R Resistor）或开关（如 DIP 开关）。

补充，stm32的NRST引脚拉低后芯片复位。



真机固件使用 FreeRTOS（抢占式 RTOS），不是简单的自研任务调度。

但是那个内置高频模块我不知道怎么设计。




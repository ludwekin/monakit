---
title: "复刻 EdgeTX 开源遥控器固件实战笔记"
description: "从 SD 卡 YAML 持久化存储、STM32 开发板选型、内部 Flash 与外扩 NOR、MTS-103 开关接法，到 CubeIDE 编译/烧录全流程。自制航模/无人机遥控器的硬件 & 软件关键点总结，适合穿越机、固定翼玩家参考。"
pubDate: "2026-03-20T14:10:00.000Z"  # 调整为当前时间附近，或保持原样
tags: 
  - EdgeTX
  - 开源遥控器
  - STM32
  - SD卡存储
  - YAML配置
  - 航模遥控
  - 无人机
  - 四轴飞行器
  - 穿越机
  - CubeIDE
  - Nucleo
  - Discovery
---






# 复刻 EdgeTX 开源遥控器固件 - 硬件 & 软件技术要点

本文档记录复刻/自制 EdgeTX 遥控器（航模/无人机开源遥控系统）时遇到的核心技术问题与解决方案。记录后经过了AI调色和排版。

## 1. SD 卡 + YAML 存储方案

**问题**：SD 卡 YAML 存储（实际持久化方案）到底有什么作用？在遥控器上是什么意义？

**回答**：

EdgeTX 从 2.5 版本开始，全面使用 **YAML** 格式存储模型和全局设置（取代旧的二进制格式）。

- 模型文件：`/MODELS/model01.yml` ～ `model60.yml`（每个模型一个 yaml 文件）
- 全局设置：`/RADIO/radio.yml`

**核心作用**：
- 真正持久化：掉电不丢，用户自定义的所有参数（混控、输入输出、曲线、逻辑开关、特效功能、遥测页等）永久保存
- 容量巨大：SD 卡轻松做到 GB 级，远超芯片内部 Flash
- 人类可读 & 可编辑：用任意文本编辑器或电脑上的 EdgeTX Companion 软件直接修改
- 支持热插拔 & 分享：改好配置插卡重启即生效，可发给别人直接用

**在自制遥控器上的实际意义**：
- 用户调参频率极高（尤其是穿越机、固定翼玩家），每次改代码重编译烧录太痛苦
- SD卡 + YAML 让用户像用专业商用遥控器一样“自己改配置、电脑编辑、即插即用”
- 是目前最友好、最贴近 EdgeTX 原生体验的持久化方案

## 2. 开发板选型

**问题**：STM32 的 Discovery 开发板和 Nucleo 开发板有什么区别？

**回答**：

| 项目           | Discovery 系列                     | Nucleo 系列                          |
|----------------|------------------------------------|--------------------------------------|
| 定位           | 功能演示 & 外设评估板              | 廉价通用原型开发板                   |
| 价格           | 明显更贵                           | 非常便宜                             |
| 板载外设       | 丰富（LCD、传感器、音频、LED矩阵等） | 极简（基本只有 ST-LINK + 晶振）      |
| 扩展性         | 一般（引脚暴露少）                 | 极强（Arduino + Morpho 双排针）      |
| 复刻遥控器推荐 | 适合初期验证特定外设驱动           | **更推荐**（引脚多、成本低、扩展方便） |

**结论**：复刻 EdgeTX 硬件时，**优先选 Nucleo**（尤其是 F4/F7 系列），Discovery 更适合学习外设。

## 3. 编译 & 调试相关

**问题**：CubeIDE 编译我的程序的过程是怎样的？

**回答**（标准流程）：

1. 预处理 → 编译（.c → .o）
2. 汇编（.s → .o）
3. 链接（.o + 启动文件 + .ld 脚本 → .elf）
4. 后处理（可选生成 .hex / .bin）

CubeIDE 默认 Build 后得到 .elf 文件，可在设置里自动转 .hex/.bin。

**问题**：CubeIDE 怎么实时看到编译出来的汇编代码？

**回答**（三种常用方法）：

方法1（最简单）：  
项目属性 → C/C++ Build → Settings → MCU GCC Compiler → Miscellaneous → 勾选  
`-save-temps` 或 `Generate .s files`  
→ 编译后项目目录出现 `xxx.s` 汇编文件

方法2（调试时看对应关系）：  
Debug 模式 → Window → Show View → Disassembly  
→ 边单步边看 C 与汇编对应

方法3（最完整）：  
终端运行：  
`arm-none-eabi-objdump -S -d your_project.elf > disasm.txt`

## 4. Flash 存储相关

**问题**：STM32 芯片（比如 F407）的 Flash 是内置的吗？

**回答**：

**是的**。几乎所有 STM32 系列（F0/F1/F2/F3/F4/F7/H7/L4 等）的**程序 Flash 都是片上集成**的（On-chip Flash），容量通常 128KB～2MB（F407 常见 512KB/1MB）。

可以通过 FSMC/FMC/QSPI 外扩 NOR/NAND/SRAM/PSRAM 等，但**固件代码始终运行在芯片内部 Flash**。

**问题**：NOR、NAND、SRAM、PSRAM、Compact Flash 这些都算 Flash 吗？Winbond W25 系列属于哪一类？

**回答**：

| 类型           | 是否 Flash | 是否非易失 | 可 XIP | 典型容量     | 典型用途                     | Winbond W25 归类 |
|----------------|------------|------------|--------|--------------|------------------------------|------------------|
| Serial NOR     | 是         | 是         | 是     | 1MB～256MB   | 固件、Bootloader、资源文件   | **属于此类**     |
| Parallel NOR   | 是         | 是         | 是     | 较小         | 老式代码存储                 | —                |
| NAND Flash     | 是         | 是         | 否     | GB 级        | 大数据（U盘、SSD）           | —                |
| SRAM           | 否         | 否         | —      | 小           | 高速缓存                     | —                |
| PSRAM          | 否         | 否         | —      | 中等         | 内存扩展                     | —                |
| Compact Flash  | 否（标准） | 是（内部 NAND） | 否 | —         | 老式存储卡                   | —                |

**Winbond W25Qxx 系列 = Serial NOR Flash（SPI/QSPI）**，复刻遥控器时最常用作外挂字体、声音、Lua 脚本等资源。

## 5. 开关硬件接法

**问题**：MTS-103 钮子开关（三档 ON-OFF-ON）的装配和接线方式？

**回答**：

**机械装配**（两个螺母）：
- 内侧螺母（定位/高度螺母）：先拧，调节开关露出面板高度（影响手感）
- 外侧螺母（固定螺母）：从面板外拧紧，把开关夹死

**电气接法**（推荐方式）：
- 中间脚（COM） → GND
- 左脚 → GPIO1（内部上拉，读 0 = 左档）
- 右脚 → GPIO2（内部上拉，读 0 = 右档）

中间档：两个 GPIO 都为 1  
这样用两个 GPIO 即可完美区分三档。

## 6. 烧录方式

**问题**：CubeIDE 写的工程怎么烧录到其他硬件（非开发板）？

**回答**（常用方法排序）：

1. **最推荐**：用 STM32CubeProgrammer + ST-LINK（SWD 接口）
2. **EdgeTX 原生方式**：SD 卡升级（把 .bin 放 FIRMWARE 文件夹 + 开机特定组合键进入 bootloader）
3. **串口 bootloader**：BOOT0 拉高 + UART + stm32flash / STM32CubeProgrammer
4. **USB DFU**：BOOT0/BOOT1 配置 + dfu-util
5. **J-Link / DAP-Link** 等第三方调试器

自制板建议预留 SWD 排针（SWDIO、SWCLK、3.3V、GND），最可靠。

---


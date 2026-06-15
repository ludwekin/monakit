论文题目拟定：基于STM32的实时无人机控制系统设计与实现  

Design and Implementation of a Real-Time UAV Control System Based on STM32


目　　　录

1 绪论
1.1 研究背景和意义
1.2 国内外研究现状
1.2.1 国内研究现状
1.2.2 国外研究现状
1.3 主要研究内容

2 系统开发技术介绍
2.1 STM32微控制器
2.2 FreeRTOS实时操作系统
2.3 IMU惯性测量单元
2.4 磁力计
2.5 气压计
2.6 无刷直流电机与ESC驱动原理
2.7 ExpressLRS遥控接收原理
2.8 嘉立创EDA与CubeMX开发环境

3 系统方案设计
3.1 系统需求分析
3.2 系统总体框架设计
3.3 系统硬件选型
3.3.1 主控芯片选型
3.3.2 惯性测量单元选型
3.3.3 磁力计模块选型
3.3.4 气压计模块选型
3.3.5 电源管理模块选型
3.3.6 Flash存储器选型
3.3.7 无线遥控接收模块选型
3.3.8 电机驱动方案选型

4 系统硬件电路设计
4.1 STM32主控电路设计
4.2 IMU惯性测量模块电路设计
4.3 磁力计模块电路设计
4.4 气压计单元电路设计
4.5 电源管理模块设计
4.6 USB通信单元设计
4.7 SPI Flash存储单元设计
4.8 PWM电机驱动接口设计
4.9 遥控接收机接口设计
4.10 PCB布局与抗干扰设计

5 系统软件设计
5.1 软件总体架构设计
5.2 FreeRTOS任务划分设计
5.3 惯性测量单元驱动程序设计
5.4 磁力计驱动程序设计
5.5 气压计驱动程序设计
5.6 姿态解算算法设计
5.7 四元数姿态表示设计
5.8 Madgwick姿态融合算法设计
5.9 PID飞行控制算法设计
5.10 PWM电机控制程序设计
5.11 数据日志与故障保护设计

6 系统实现与测试
6.1 硬件实现
6.2 系统功能测试
6.2.1 初始化测试
6.2.1 传感器数据测试
6.2.2 姿态解算测试
6.2.3 PWM输出测试

7 总结

参考文献

致谢



系统框架图？？

实际飞控：stm32f405rgt6,icm42607-p,bmp280,w25q256,成品elrs接收机，dcdc升压模块（1节锂电池升到5v），ams1117-3.3,4pin串口，4pin调试swd接口，4pin串口（接光流传感器），4pin的i2c接口（接磁力计），


不管怎么样，优先注意以下的话术：
以上内容被检测出AIGC 帮我润色修改，使其更复合本科论文水平，要求如下：
1. 在不大幅改动原文总字数的情况下，只调整语序、替换同义词、变换主谓宾结构，补充那些无主语句的主语，语言简化，让语句有逻辑且通顺，贴合基础论文写作规范。 
2. 弱化专业感，要营造作者写起来比较吃力、勉强写完了的普通文笔效果，删除“我觉得、我认为”这些主观表述，整体文笔平实普通。
3. 弱化语句精炼度，贴合新手写作状态，但是字数不要增加，保持和原文差不多，稍微增加一点也可以。
4. 减少句号使用，多用逗号、分号衔接；将长句拆分成短句，高频词换同义词，专业词汇替换为通俗简单表达。
5. 打乱句子原有结构，灵活互换，把字句、被动句，调整语句语序，不改变原文核心表意。删除过于口水话的口语化表达，保持基本语言逻辑,严格执行。6.不用太多对称的句式结构和关联词，长短句结合，少用短句。短句多的话，把短的句子改成长句子，少用顿号、逗号、关联词，少用比如、例如，首先其次最后，少举例，重复观点的话可直接删除，如果是很晦涩的句子要转化成通俗的语言，也不要太过口语化，不要用排比句，不要用“以下几个方面：1..2.”这样的结构或者“A+B”这样的创造性短语。 
7.字数少一点，不要使用口语化词语句子，不要使用口语化词语和句子，这是最重要的


1. CubeMX 配置：
启用 Use Newlib Reentrant（如果用 printf 等）。
启用 Preemption（抢占式调度，这是 FreeRTOS 的核心优势）。
Sensor/Control 给 512-1024 words（STM32 RAM 有限，注意别溢出）。

2. 任务间通信非常重要：
Queue（队列）：Sensor → Estimation → Control（传递原始数据或融合结果）。
Mutex：保护共享资源（如全局姿态数据），但高频任务中少用（会阻塞）。
Event Groups / Semaphore：用于中断唤醒任务（比如 UART 收到 CRSF 帧）。
Shared Memory + volatile：高频控制数据（姿态、PID 输出），配合 Mutex 或 careful design。

3. Queue（队列）：
freertos里面queue的作用？
在 FreeRTOS 中，队列（Queue） 是其核心的 IPC（进程间通信）机制。
- 任务间数据传递
它传递的是数据的副本（而非指针），这避免了多任务同时访问同一内存区域的风险。
例如：传感器任务将采集到的温度值 (int) 发送给显示任务；串口接收任务将字符数组发送给协议解析任务。
- 任务与中断同步
队列可以作为中断服务程序（ISR）与任务之间的安全桥梁。
在 ISR 中使用 xQueueSendFromISR()，在任务中使用 xQueueReceive()。
当硬件事件发生时（如按键按下、DMA 传输完成），ISR 通过队列发送一个"通知"或"空结构体"，唤醒等待的任务去处理后续耗时操作，而 ISR 快速退出。
- 实现"生产者-消费者"模型
队列天然支持多生产者、多消费者。多个任务可以向同一个队列发送消息。
多个任务可以等待同一个队列的消息（通常配合优先级使用）。当消息到达时，只有等待中优先级最高的任务会被唤醒并获得消息。
3. 代码：
ControlTask用 osDelayUntil 实现精确周期，比 osDelay 好很多。
Core/Src/freertos.c（CubeMX 生成的任务创建和初始化在这里）。
我可以新建 Tasks/ 或 Application/ 文件夹放自定义任务代码。
所有用户代码尽量放在 /* USER CODE BEGIN */ 和 /* USER CODE END */ 之间，重新生成 CubeMX 时不会被覆盖。
记得定义共享的数据结构体（新建一个 flight_data.h）。
``` // flight_data.h
#ifndef FLIGHT_DATA_H
#define FLIGHT_DATA_H

#include "cmsis_os.h"   // 必须包含这个

typedef struct {
    float gx, gy, gz;     // 陀螺
    float ax, ay, az;     // 加速度
    uint32_t timestamp;
} IMU_Data_t;

typedef struct {
    float roll, pitch, yaw;
    float q[4];           // 四元数
    uint8_t dataReady;
} Attitude_t;

// 全局实例（推荐 extern 在 .h，定义在 .c）
extern Attitude_t attitude;
extern osMessageQueueId_t imuQueueHandle;   // CubeMX 会生成

#endif
``` 
在 freertos.c 或新建的任务文件里写任务。
Sensor Task 示例：
``` 
// SensorTask.c
#include "flight_data.h"
#include "cmsis_os.h"

void SensorTask(void *argument)
{
    IMU_Data_t imuData = {0};
    uint32_t lastWakeTime = osKernelGetTickCount();
    
    for(;;)
    {
        // TODO: 这里放你的 IMU 读取代码 (SPI/I2C)
        // imuData.gx = mpu6050_read_gx(); ...
        
        imuData.timestamp = osKernelGetTickCount();
        
        // 发送到队列（不等待，防止卡住）
        osMessageQueuePut(imuQueueHandle, &imuData, 0U, 0U);
        
        osDelayUntil(&lastWakeTime, 1);   // 精确 1ms 周期
    }
}
``` 
Control Task 示例:
``` 
// ControlTask.c
#include "flight_data.h"
#include "cmsis_os.h"

void ControlTask(void *argument)
{
    IMU_Data_t imuRecv = {0};
    uint32_t lastWakeTime = osKernelGetTickCount();
    
    for(;;)
    {
        // 从队列取数据，最多等待 5 ticks（5ms）
        if (osMessageQueueGet(imuQueueHandle, &imuRecv, NULL, 5) == osOK)
        {
            // 这里做姿态融合（Madgwick / Kalman）
            // 更新全局姿态
            attitude.roll = ...;
            attitude.pitch = ...;
            attitude.dataReady = 1;
        }
        
        // 执行 PID 控制 → 输出电机
        // motor_output(...);
        
        osDelayUntil(&lastWakeTime, 2);   // 500Hz
    }
}
``` 

CRSF 接收task（包含Event Flags）:
``` 
// CRSFTask.c
#include "flight_data.h"
#include "cmsis_os.h"
// #include "crsf.h"   // 你的CRSF解析库

void CRSFTask(void *argument)
{
    for(;;)
    {
        // 等待 UART 中断发来的事件
        osEventFlagsWait(uartEventHandle, 0x01, osFlagsWaitAny, osWaitForever);

        // 处理接收到的 CRFS 数据
        // CRSF_ProcessFrame();
        // 更新遥控通道值（建议再用一个 rcQueue 或共享变量给 ControlTask）
    }
}

// ============== UART 中断回调（放在 stm32xx_it.c 或 uart.c） ==============
void HAL_UART_RxCpltCallback(UART_HandleTypeDef *huart)
{
    if (huart == &huartx)   // 换成你的 CRSF UART
    {
        BaseType_t xHigherPriorityTaskWoken = pdFALSE;
        osEventFlagsSet(uartEventHandle, 0x01, &xHigherPriorityTaskWoken);   // CMSIS V2
        portYIELD_FROM_ISR(xHigherPriorityTaskWoken);
    }
}
``` 
freertos.c：
在 freertos.c 的 MX_FREERTOS_Init(void) 函数里，USER CODE BEGIN Init 区域添加：
``` 
/* USER CODE BEGIN Init */

// 创建 Queue（CubeMX 已创建的话就不用重复创建）
imuQueueHandle = osMessageQueueNew(8, sizeof(IMU_Data_t), NULL);

// 创建 Mutex
attitudeMutexHandle = osMutexNew(NULL);

// 创建 Event Flags
uartEventHandle = osEventFlagsNew(NULL);

// 创建任务
osThreadId_t sensorTaskHandle;
const osThreadAttr_t sensor_attributes = {
    .name = "Sensor",
    .stack_size = 1024,           // 字节
    .priority = osPriorityHigh,
};
sensorTaskHandle = osThreadNew(SensorTask, NULL, &sensor_attributes);

osThreadId_t controlTaskHandle;
const osThreadAttr_t control_attributes = {
    .name = "Control",
    .stack_size = 2048,
    .priority = osPriorityHigh,
};
controlTaskHandle = osThreadNew(ControlTask, NULL, &control_attributes);

osThreadId_t crsfTaskHandle;
const osThreadAttr_t crsf_attributes = {
    .name = "CRSF",
    .stack_size = 1024,
    .priority = osPriorityAboveNormal,
};
crsfTaskHandle = osThreadNew(CRSFTask, NULL, &crsf_attributes);

/* USER CODE END Init */
``` 
补充：freertos.c 是 FreeRTOS 初始化和任务管理的主入口文件。CubeMX 在你启用 FreeRTOS（CMSIS V2）后，会自动生成这个文件。
MX_FREERTOS_Init() 函数 ，这是整个 FreeRTOS 的初始化函数。会在 main.c 里的 main() 函数中被调用（通常在 MX_Init() 之后）。负责创建 Queue、Mutex、Event Flags、Semaphore 等 RTOS 对象。负责创建你定义的所有 任务（Task）。

main.c:
在这个项目里面main.c 的作用?
- 程序启动第一站（C 语言的 main() 函数）。
- 负责硬件初始化（时钟、GPIO、UART、SPI、I2C、定时器、ADC 等）。
- 调用 MX_FREERTOS_Init() 来初始化 FreeRTOS 和创建任务。
- 最后启动 FreeRTOS 调度器（osKernelStart()），之后就进入多任务世界了。
- main 函数执行完后不会再回来（被 FreeRTOS 接管）。
main.c 典型结构：
``` 
/* main.c */
#include "main.h"
#include "cmsis_os.h"          // 必须包含
#include "flight_data.h"       // 你自己建的头文件

int main(void)
{
    /* USER CODE BEGIN 1 */
    /* USER CODE END 1 */

    /* 硬件初始化（CubeMX 生成的） */
    HAL_Init();                    // HAL 库初始化
    SystemClock_Config();          // 系统时钟配置
    MX_GPIO_Init();
    MX_SPI1_Init();                // 你的 IMU 可能是 SPI
    MX_USART1_UART_Init();         // CRSF 用的 UART
    MX_TIMx_Init();                // PWM 定时器等
    /* ... 其他外设初始化 */

    /* USER CODE BEGIN 2 */
    /* USER CODE END 2 */

    /* 初始化 FreeRTOS + 创建所有任务 */
    MX_FREERTOS_Init();            // ← 关键！调用 freertos.c 里的函数

    /* 启动 FreeRTOS 调度器 */
    osKernelStart();               // ← 从这里开始多任务运行

    /* 理论上永远不会执行到这里 */
    while (1)
    {
    }
}
``` 






















4. Mutex:
CubeMX 里添加 Mutex 后，记得在初始化时 osMutexNew()（自动生成）。
添加 Mutex（保护 attitude），Name: attitudeMutex。
添加 Event Flags（给 CRSF 用），Name: uartEvent。
生成代码后，CubeMX 会在 freertos.c 里自动创建句柄（imuQueueHandle、attitudeMutexHandle 等）。



5. CMakeLists.txt:
CubeMX 生成的 CMake 项目通常是这样的:
``` 
ProjectRoot/
├── CMakeLists.txt                  ← 你主要修改这个（用户文件，不会经常被覆盖）
├── STM32CubeMX/                    ← CubeMX 生成的文件（会被覆盖）
│   ├── CMakeLists.txt
│   └── cmake/
│       └── stm32cubemx/
│           └── CMakeLists.txt
├── Core/
│   ├── Src/
│   │   ├── main.c
│   │   ├── freertos.c
│   │   ├── stm32xx_it.c
│   │   └── ... 
│   └── Inc/
├── Middlewares/
├── Drivers/
├── Tasks/                          ← 建议你新建这个文件夹放自定义任务
│   ├── SensorTask.c
│   ├── ControlTask.c
│   ├── CRSFTask.c
│   └── ...
├── flight_data.h                   ← 放在 Core/Inc 或新建 Application/Inc
└── ...
``` 
记得在根目录 CMakeLists.txt 中添加文件（推荐方式）：
```
# ====================== 用户自定义源文件 ======================
set(USER_SOURCES
    # 你的自定义任务文件
    ${CMAKE_CURRENT_SOURCE_DIR}/Tasks/SensorTask.c
    ${CMAKE_CURRENT_SOURCE_DIR}/Tasks/ControlTask.c
    ${CMAKE_CURRENT_SOURCE_DIR}/Tasks/CRSFTask.c
    # 如果还有其他 .c 文件，继续添加
    
    # main.c 和 freertos.c 通常已经被 CubeMX 包含了，不需要重复加
)

# 如果使用 file(GLOB) 方式（更方便，但不推荐用于生产）
# file(GLOB USER_SOURCES 
#     ${CMAKE_CURRENT_SOURCE_DIR}/Tasks/*.c
# )

# 添加到可执行目标（CubeMX 生成的目标名通常是 ${CMAKE_PROJECT_NAME} 或 stm32cubemx）
target_sources(${CMAKE_PROJECT_NAME} PRIVATE ${USER_SOURCES})

# ====================== 添加头文件路径 ======================
target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/Core/Inc
    ${CMAKE_CURRENT_SOURCE_DIR}/Tasks                # 如果头文件也在 Tasks 里
    ${CMAKE_CURRENT_SOURCE_DIR}/Application/Inc     # 推荐新建这个文件夹放 flight_data.h
)
```
6. 状态机
flight_state.h:
``` 
typedef enum {
    STATE_INIT = 0,           // 上电初始化
    STATE_WAIT_RX,            // 等待 ELRS 连接
    STATE_READY,              // 已连接，可 Arm（检查角度）
    STATE_ARMED,              // 已 Arm，电机怠速
    STATE_FLYING,             // 正在飞行
    STATE_FAILSAFE,           // 失控保护
    STATE_ERROR               // 严重错误
} FlightState_t;

extern FlightState_t currentState;
extern char* stateString[];   // 用于打印状态
``` 
在 ControlTask 中增加状态机主逻辑:
``` 
void ControlTask(void *argument)
{
    uint32_t lastWakeTime = osKernelGetTickCount();
    
    for(;;)
    {
        // 1. 获取最新姿态和遥控数据
        // 2. 状态机处理
        switch(currentState)
        {
            case STATE_WAIT_RX:
                if (CRSF_IsLinked()) {
                    currentState = STATE_READY;
                    Buzzer_Beep(3, 100);   // 滴滴滴
                }
                break;

            case STATE_READY:
                if (Attitude_Within_30_Deg() == false) {
                    // 角度太大，禁止 Arm，LED 红闪
                }
                if (CRSF_IsArmed()) {
                    currentState = STATE_ARMED;
                    Buzzer_Beep_Long();
                }
                break;

            case STATE_ARMED:
                if (CRSF_GetThrottle() > 1050) {   // 推油门起飞
                    currentState = STATE_FLYING;
                }
                // 保持低怠速 (如 1050~1100)
                Set_All_Motors(1100);   
                break;

            case STATE_FLYING:
                // 执行角度模式 PID 控制
                Angle_Mode_Control();
                break;

            default:
                break;
        }

        osDelayUntil(&lastWakeTime, 2);   // 500Hz
    }
}
``` 







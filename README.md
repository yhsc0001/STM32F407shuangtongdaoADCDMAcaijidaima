# STM32F407 双通道ADC DMA采集代码

## 项目简介

本仓库提供了一套详细的STM32F407微控制器利用HAL库实现的双通道ADC通过DMA进行数据采集的示例代码。该方案特别适用于需要高效、实时数据采集的应用场景，例如在环境监测、精确控制等领域。本代码配置了两个ADC通道：第一个通道连接到PA3，用于读取外部光敏电阻的变化，从而反应光照强度；第二个通道则利用STM32F407自带的内部温度传感器，实现了对芯片自身温度的监控。采集到的数据通过USART（通用同步异步收发器）发送至电脑或其他外设，方便用户实时分析和显示数据。

## 技术栈

- **MCU**: STM32F407 (基于ARM Cortex-M4)
- **库**: HAL库 (Hardware Abstraction Layer)
- **功能模块**: ADC, DMA, USART
- **应用**: 数据采集, 实时监测

## 特性

1. **双通道ADC同时采样**：一个用于外部输入（PA3，光敏电阻），另一个用于内部温度测量。
2. **DMA传输**：高效地将ADC数据转移到内存中，减轻CPU负担。
3. **串口输出**：通过USART将采集到的数据实时发送到计算机或者其他串口设备上。
4. **示例驱动**：完整示例代码，易于理解与快速上手。

## 快速入门

### 硬件需求

- STM32F407开发板
- 光敏电阻连接到PA3
- 连接到PC的USB转串口线

### 软件准备

1. 安装STM32CubeMX来生成初始化代码。
2. 下载或克隆本仓库到本地。
3. 使用Keil/STM32CubeIDE等IDE打开项目。
4. 根据具体硬件配置STM32CubeMX中的引脚和外设选项。

### 编译与运行

- 在IDE中编译项目。
- 将生成的hex文件烧录到STM32F407开发板。
- 使用串口助手工具，配置正确的波特率（如115200bps），查看输出数据。

## 注意事项

- 确保你的开发环境已正确设置HAL库路径。
- 根据实际使用的硬件调整相关引脚配置和参数。
- 测试之前，请检查电路连接是否正确，避免硬件损坏。

## 示例代码结构

- `main.c` 包含主函数及系统初始化。
- `stm32f4xx_hal_msp.c` 中有中断服务程序的声明。
- `stm32f4xx_it.c` 可能包含DMA完成回调等中断处理逻辑。
- 配置文件如`stm32f4xx_hal_conf.h`确保HAL库正确配置。

## 开源许可

本项目遵循MIT许可证，欢迎大家fork、贡献以及在遵守许可证条款的前提下自由使用。

---

通过此代码示例，开发者可以快速掌握如何在STM32F407上利用HAL库高效执行双通道ADC的数据采集，并通过DMA简化数据传输流程，进一步增强嵌入式系统的设计能力。

## 下载链接
[STM32F407双通道ADCDMA采集代码](https://pan.quark.cn/s/c69dca724336) 

(备用: [备用下载](https://pan.baidu.com/s/1MIqhxfonNeo9PPEU6jdbRg?pwd=1234))

## 说明

该仓库仅用于学习交流，请勿用于商业用途。

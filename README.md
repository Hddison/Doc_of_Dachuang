# STM32F407VET6 热成像针孔相机检测仪

## 项目简介
本项目基于STM32F407VET6微控制器开发便携式热成像检测设备，用于识别酒店场景中的隐蔽针孔摄像头。系统通过红外热成像技术检测异常热源特征，结合图像处理算法实现自动化识别。

## 核心功能
- 红外热成像数据采集（支持MLX90640等传感器）
- 实时温度场可视化（通过OLED/LCD显示）
- 针孔摄像头特征识别算法
- 异常报警与位置标记
- 数据存储与导出（支持SD卡）

## ov2640尺寸图
![OV2640](https://www.waveshare.net/w/upload/d/d5/OV9655-2640-Camera-Board-size.jpg)


## 硬件组成
| 模块          | 型号               | 连接方式  | 功能说明            |
|---------------|--------------------|-----------|---------------------|
| 主控芯片      | STM32F407VET6      | -         | 主处理器            |
| 热成像模块    | MLX90640           | I2C       | 红外温度检测        |
| 可见光摄像头  | OV2640             | DCMI      | 辅助图像采集        |
| 显示模块      | 1.3寸OLED          | SPI       | 实时数据显示        |
| 存储模块      | microSD卡槽        | SDIO      | 数据存储            |
| 电源管理      | 5V/2A电源适配器    | USB       | 系统供电            |

## 软件架构
```plaintext
├── Drivers/
│   ├── STM32CubeMX配置
│   └── HAL库定制
├── Middlewares/
│   ├── MLX90640驱动
│   └── OpenCV精简版
├── Source/
│   ├── thermal_processing.c  # 热成像数据处理
│   ├── camera_capture.c      # 图像采集
│   └── detection_algorithm.c # 核心检测算法
└── Projects/
    └── STM32F407ZGTx_FLASH.ld # 链接脚本

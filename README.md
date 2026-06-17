# ROS Robot Portfolio

<div align="center">

**鲁江龙 | Robotics & AI Engineer**

ROS开发 | 导航规划 | 多传感器融合 | 机械臂控制 | 边缘AI部署 | 具身智能

</div>

---

## 关于本仓库

人工智能专业本科在读，专注于移动机器人、导航定位、多传感器融合及具身智能方向。

本仓库记录了我在 ROS 机器人开发、嵌入式系统、边缘 AI 部署等方向的完整项目实践，涵盖从算法验证、系统集成到部署调试的全流程。

---

## 技术栈

<details open>
<summary><b>机器人框架</b></summary>

ROS1 / ROS2 · TF / TF2 · Navigation（MoveBase / Nav2）· RViz · Gazebo · MoveIt

</details>

<details open>
<summary><b>导航与规划</b></summary>

GMapping · AMCL · Costmap2D · A* 路径规划 · DWA 局部规划器 · Behavior Tree（基础）

</details>

<details open>
<summary><b>状态估计与控制</b></summary>

EKF 多传感器融合（robot_localization）· 差速运动学建模 · PID 控制与参数调优

</details>

<details open>
<summary><b>视觉感知</b></summary>

YOLOv5 / YOLOv8 · OpenCV · ARTag 位姿估计

</details>

<details open>
<summary><b>嵌入式与硬件</b></summary>

STM32（F103 / F401）· RT-Thread · FreeRTOS · LVGL · SPI / I2C · IMU / 编码器

</details>

<details open>
<summary><b>通信</b></summary>

UART · CAN · TCP/IP · UDP · MQTT · ZigBee

</details>

<details open>
<summary><b>AI 部署</b></summary>

RK3588 / RKNN / RKNPU · ONNX · TensorRT（基础）· 嵌入式端侧 CNN 推理

</details>

<details open>
<summary><b>开发语言与工具</b></summary>

C++ · Python · C · Linux（Ubuntu）· CMake · Git

</details>

---

## 项目

### 1. 自主导航与目标识别机器人

> 基于 ROS 的竞赛机器人，实现 SLAM 建图、自主导航、目标识别与打击全流程

**技术栈：** `ROS1` `GMapping` `AMCL` `MoveBase` `Navigation` `TF` `YOLOv8` `OpenCV` `PID`

- 基于 GMapping 构建二维栅格地图，AMCL 实现自主定位
- 基于 MoveBase 框架完成全局路径规划与 DWA 局部避障
- 阅读 Navigation 框架源码，理解 Costmap 与 DWA 工作机制，针对性调优参数
- 结合 YOLOv8 与 ARTag 完成目标检测与位姿解算，通过 TF 完成坐标转换与目标跟踪
- **成果：** 真实场景稳定运行，获全球校园人工智能算法精英大赛**国家级二等奖**、机器人及人工智能大赛**国家级三等奖**

---

### 2. 移动机械臂协同抓取系统

> 移动平台自主导航 + 机械臂运动规划，实现协同抓取闭环

**技术栈：** `ROS1` `MoveIt` `Gazebo` `RViz` `TF` `OpenCV` `ARTag`

- 基于 Navigation 完成底盘自主导航
- 利用 TF 建立 map、odom、base_link 与机械臂坐标系关系，实现目标空间映射
- 结合 OpenCV 与 ARTag 获取目标位姿，基于 MoveIt 实现逆运动学求解与轨迹规划
- 在 Gazebo 中完成仿真验证，实现导航 + 抓取全流程闭环

---

### 3. EKF 多传感器融合定位系统

> 融合编码器里程计与 IMU 数据，提升轮式机器人定位精度

**技术栈：** `ROS1` `robot_localization` `EKF` `STM32` `IMU` `TF` `RViz` `Python`

- 基于 robot_localization 构建 EKF 融合模型，融合 STM32 编码器里程计与 MPU6050 IMU 数据
- 完成 map → odom → base_link TF 树构建
- 调整过程噪声与观测噪声协方差矩阵优化滤波效果
- **成果：** 显著降低定位漂移，提高导航稳定性与轨迹跟踪精度

---

### 4. 智慧农业环境监测系统

> 基于边缘 AI 与多传感协同的温室环境监测与自动调控

**技术栈：** `STM32` `RT-Thread` `OpenHarmony` `MQTT` `ZigBee` `Python`

- 基于 STM32 与 RT-Thread 实现温湿度、光照及土壤湿度数据采集
- 利用 ZigBee 与 MQTT 建立边缘节点通信链路
- 引入模糊控制算法与积分灌溉策略实现自动控制
- **成果：** 获计算机设计大赛**省级二等奖**、服创赛**省级三等奖**

---

### 5. YOLO 垃圾检测系统（RK3588 边缘部署）

> 模型轻量化 + 边缘端实时推理

**技术栈：** `YOLOv8` `RK3588` `RKNN` `RKNPU` `Linux`

- 基于 YOLOv8 完成垃圾分类模型训练
- 利用 RKNN Toolkit 进行模型转换与 INT8 量化
- 部署至 RK3588 平台，调用 RKNPU 硬件加速实现边缘实时推理

---

### 6. 边缘视觉 AI 手势博弈系统

> 在 STM32 上纯 C 实现 CNN 推理，完成端侧手势识别与博弈交互

**技术栈：** `STM32F103` `RT-Thread` `OV2640` `CNN` `FSM` `C`

- 基于 STM32F103 与 OV2640 实现图像采集
- 对 PyTorch 训练模型进行轻量化重构，纯 C 实现 CNN 推理算子并优化内存复用
- 利用 FSM 状态机实现完整交互流程

---

### 7. 智能手表 GUI 开发

> 基于 FreeRTOS 多任务架构 + LVGL 图形界面 + 触摸交互

**技术栈：** `STM32F401` `FreeRTOS` `LVGL` `GC9A01 LCD` `CST816D` `RTC` `SPI` `I2C` `CubeMX`

- 基于 CubeMX 配置 FreeRTOS 多任务框架，设计 HomeTask、TaskLvgl 等独立任务
- 利用软件定时器与消息队列实现 RTC 时间数据的周期采集与任务间通信
- 采用互斥信号量保护 LVGL 屏幕资源
- 通过 SPI 驱动 GC9A01 LCD，I2C 完成 CST816D 触摸数据采集与手势识别
- **成果：** 支持实时时钟显示、触摸手势滑动切换页面、按钮计数等功能，运行稳定流畅

---

### 8. VLA 机械臂模仿学习系统

> 基于 Vision-Language-Action 模型的端到端模仿学习，探索具身智能在低成本硬件上的可行性

**技术栈：** `PyTorch` `HuggingFace LeRobot` `ACT` `SmolVLA (0.45B)` `Diffusion Policy` `RealSense D435i` `SO-100` `MuJoCo` `Accelerate` `wandb`

- 搭建 RealSense D435i + SO-100 Leader-Follower 遥操作系统采集视觉-动作示教数据
- 基于 LeRobot 框架集成 ACT、SmolVLA、Diffusion Policy 等前沿策略
- 利用 Accelerate 实现分布式混合精度训练与 wandb 监控
- 完成 MuJoCo 仿真评估后部署至实机闭环验证
- **成果：** 构建 **数据采集 → 策略训练 → 仿真评估 → 实机部署** 完整具身智能开发流程，在低成本硬件上验证多种前沿模仿学习算法有效性

---

## 竞赛获奖

| 奖项 | 级别 | 年份 |
|:---|:---|:---|
| 全球校园人工智能算法精英大赛全国总决赛（视觉巡航赛） | 国家级二等奖（A类） | 2025 |
| 中国机器人及人工智能大赛全国总决赛（目标射击赛项） | 国家级三等奖（A类） | 2025 |
| 中国大学生计算机设计大赛（人工智能应用实践赛） | 省级二等奖（A类） | 2026 |
| 中国大学生服务外包创新创业大赛（A03 智慧农业赛题） | 省级三等奖（A类） | 2026 |
| 睿抗机器人开发者大赛（魔力元宝服务组） | 省级三等奖（A类） | 2025 |

---

## 联系方式

Email：lelaj666@gmail.com

GitHub：[github.com/Lelaj666](https://github.com/lelaj666)

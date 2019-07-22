# ROVER & Mission Planner Operation Instruction

## 一 飞控连接地面站
### 1.1 连接USB
首先，我们需要下载一个地面站. 从 www.ardupilot.org 这个Ardupilot的官网中，点击 DOCS. 从而进入地面站下载界面
目前，有两种官方地面站，一种是 Mission Planner, 另一种就是 APM 2. 这两种地面站均可以和我们目前使用的 Pixhawk相互配合, 但是目前存在 APM 2 的 ROVER 固件版本较低， 为 3.4.2。 但是在 Mission Planner上面的 ROVER 固件版本为 3.5.1. 由于在前期 Mission Planner存在驱动安装不完全，导致无法刷新固件 3.5.1. 前期我采用了APM 2 的 3.4.2 的固件. 但是目前我已经用 Mission Planner 安装了最新固件 3.5.1.

### 1.2 下载固件
下图为APM2下载固件界面，APM2目前只提供 ArduRover 3.4.2版本
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%9B%BA%E4%BB%B6%E5%AE%89%E8%A3%85.JPG)
下图为 Mission Planner的下载固件界面，在途中我们可以看到 Mission Planner的固件种类更为丰富，而且版本较新，推荐使用 Mission Planner 来作为地面站和固件下载平台
![image](https://github.com/wzezhong/Rover/blob/master/images/MP.JPG)

#### 注意事项
下载固件时请注意，请勿点击右上角的连接标志， 按照提示来，地面站下载完成固件时会提醒先拔出USB线，然后在电脑上点击OK键，随后在30秒内重新插入飞控USB线. 直到最后听见蜂鸣器有音乐声再点击电脑上的OK. 到此固件更新完成.

#### 飞控连接不上电脑的原因
1. 缺少相关的系统驱动
2. 有可能是飞控的供电不足引起无法连接电脑，此问题在调试中发生多次，以后开发如遇见类似问题可采用USB连接电脑，同时对飞控进行外部供电. 或者换一根USB线
3. 飞控内存卡没有插好

## 二 参数校准
### 2.1 加速度计校准
首先连接地面站， 下载好固件之后，点击右上角的连接标志，在成功连接之后会出现下面的图示， 此时在安装固件截面会出现以下的提示，证明此时的连接已经成功
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%BF%9E%E6%8E%A5%E6%8F%90%E7%A4%BA.JPG)

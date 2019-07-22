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
接下来开始校准加速度计， 点击INITIAL SETUP --→ Mandatory Hardware --→ Accel Calibration
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E6%A0%A1%E5%87%86%E7%95%8C%E9%9D%A2.JPG)
我们点击 Calibrate Accel, 然后根据提示来对飞控的不同方向进行加速度计校准. 看下面的步骤，首先是水平，在平面放置好飞控后稳住，点击 Click when Done
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E6%B0%B4%E5%B9%B3%E6%A0%A1%E5%87%86.JPG)
下面是左侧校准， 有USB接口的是飞控的右侧
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E5%B7%A6%E4%BE%A7%E6%A0%A1%E5%87%86.JPG)
接下来是右侧的校准， 稳住点击 Click when Done
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E5%8F%B3%E4%BE%A7%E6%A0%A1%E5%87%86.JPG)
前面的校准， 飞控上面的箭头指示方向为前方
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E5%90%91%E5%89%8D%E6%A0%A1%E5%87%86.JPG)
后侧校准
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E5%90%91%E5%90%8E%E6%A0%A1%E5%87%86.JPG)
背部校准， 把飞控翻过来平放
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E8%83%8C%E9%9D%A2%E6%A0%A1%E5%87%86.JPG)
加速度计校准完成
![image](https://github.com/wzezhong/Rover/blob/master/images/%E5%8A%A0%E9%80%9F%E5%BA%A6%E8%AE%A1%E6%A0%A1%E5%87%86%E5%AE%8C%E6%88%90.JPG)
进行加速度计校准的最后一项，校准水平， 把飞控平放，点击 Calibrate Level. 此项校准目的是在安装飞控后，或者校准过飞控后又移动了飞控的位置，导致无人车水平放置时，飞控没有处于水平位置. 根据提示，水平放置后保持静止，等待几秒钟就好
![image](https://github.com/wzezhong/Rover/blob/master/images/%E6%A0%A1%E5%87%86%E6%B0%B4%E5%B9%B3.JPG)
所有校准完成界面
![image](https://github.com/wzezhong/Rover/blob/master/images/%E6%B0%B4%E5%B9%B3%E6%A0%A1%E5%87%86%E5%AE%8C%E6%88%90.JPG)

### 2.2 罗盘校准
如下图, 罗盘未校准完成时, OFFSET的数值均为红色（因为我们的飞控有一个罗盘， 还有一个磁罗盘）. 所以我们需要校准的是两个罗盘分别对应下方的 Mag1 & Mag2

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
#### 开始校准前请插上GPS模块并遵从上图的所有选项以避免罗盘校准失误，且罗盘校准对周围环境要求很高，在我多次尝试失败后，在开阔地等磁性较小的地方校准最为准确。
点击 Pixhawk/PX4
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%82%B9%E5%87%BB%E6%A0%A1%E5%87%86%E7%BD%97%E7%9B%98.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E6%A1%86.JPG)

![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E7%95%8C%E9%9D%A2%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9.JPG)
开始校准
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E5%BC%80%E5%A7%8B.JPG)
#### 注意，Pixhawk罗盘的磁性非常敏感，尽量不要把罗盘放在距离磁性物质很近的地方，以免发生罗盘短暂失效或永久失效的情况发生
下图为错误的“罗盘校准成功”界面， 正是因为罗盘短暂失效，所以没有第2个罗盘的读数，一定要注意
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E6%88%90%E5%8A%9F.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E6%88%90%E5%8A%9F2.JPG)
#### 罗盘校准经过总结后得出, 罗盘设定中一共6个面，共3个维度，但只要取6个面中的3个覆盖3个维度即可，对着地面，依次顺时针转几圈再逆时针转几圈重复此动作直到罗盘校准提示成功
下面图示诶正确的罗盘校准过程
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E6%A0%A1%E5%87%86%E8%BF%87%E7%A8%8B%E6%9B%B4%E6%96%B0.JPG)
有可能会出现2个进度条一个充满另一个不满的情况，这是正常情况，充满的进度条会重新采集数据，持续转动飞控，直到两个进度条都充满为止，并弹出以下窗口，才算是成功.
![image](https://github.com/wzezhong/Rover/blob/master/images/%E7%BD%97%E7%9B%98%E7%9C%9F%E6%AD%A3%E6%A0%A1%E5%87%86%E6%88%90%E5%8A%9F.JPG)
#### 注意
点击OK后要给飞控完全断电，然后重新连接飞控至电脑，再点击地面站的右上角，此时才能看到两个罗盘的坐标值都为绿色

### 2.3遥控器校准
点击左侧的 Radio Calibration， 开始进行遥控器校准作业 注意，此时一定要把接收机连接上飞控
校准前的步骤
1. 正确连接接收机
2. 打开遥控器, 并讲遥控器和接收机对码连接
3. 连接正常后，地面站和遥控器如图显示
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%81%A5%E6%8E%A7%E6%A0%A1%E5%87%86%E7%95%8C%E9%9D%A2.JPG)
点击 Calibrate Radio, 弹出对话框. 提示为确认无人车处于启动状态， 并且接收机已经供电并且连接飞控（为了安全保证， 让轮子悬空，即使出现意外情况转起来也不会造成伤害）
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%81%A5%E6%8E%A7%E6%A0%A1%E5%87%86%E5%AF%B9%E8%AF%9D%E6%A1%86.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%81%A5%E6%8E%A7%E6%A0%A1%E5%87%86%E5%AF%B9%E8%AF%9D%E6%A1%862.JPG)
根据上图提示，点击OK之后，拨动遥控器的所有摇杆和开关到他们的极限位置，然后会显示他们的极限数值
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%81%A5%E6%8E%A7%E5%99%A8%E6%A0%A1%E5%87%86%E5%AE%8C%E6%88%90.JPG)
点击OK后， 地面站会将得到的数据写入飞控
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%81%A5%E6%8E%A7%E5%99%A8%E6%A0%A1%E5%87%86%E5%AE%8C%E6%88%902.JPG)
至此，遥控器校准全部完成

### 2.4 设置飞行模式
我们使用的遥控器有多种飞行模式可以选择，在飞行模式设置完成后，我们可以在小车测试时直接通过我们的遥控器来选择不同的小车行驶模式，这其中包含了如自动行驶，自动返航等模式。我们只需在下列的模式选项表中分配好（1-6）分别对应的行驶模式
如下图所示， 当前的PWM： 8:1526 （当前的mode设置使用的PWM通道是8通道，当前值是1526)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%A3%9E%E8%A1%8C%E6%A8%A1%E5%BC%8F%E8%AE%BE%E7%BD%AE1.JPG)
转动我们遥控器上方的两个旋钮，会发现屏幕上绿色光标会相应的移动，根据遥控器上相应的通道具有的档位数量，可以设置不同数量的飞行模式. 点击绿色光标所在的下拉窗口，可以选择不同的飞行模式.
Manual 手动
Auto 自动
RTL 自动返航，走直线到初始位置
Hold 保持当前位置
SmartRTL 自动返航，走原始路线返航到初始位置
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%A3%9E%E8%A1%8C%E6%A8%A1%E5%BC%8F%E8%AE%BE%E7%BD%AE2.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%A3%9E%E8%A1%8C%E6%A8%A1%E5%BC%8F%E8%AE%BE%E7%BD%AE%E5%AE%8C%E6%88%90.JPG)

### 2.5 Servo Output
![image](https://github.com/wzezhong/Rover/blob/master/images/Servo%20Output.JPG)
该界面左侧一列和故障保护界面右侧一列的电机输出功能类似。不同的是，功能侧重点不一样。该界面主要侧重于输出通道的设置。解释如下
Position当前通道的输出数值大小
Rever 通道反向。点击后输出的 PWM 波反向。
Function当前通道输出的函数。
Min当前通道可以输出 PWM 信号数值的最小值
Trim当前通道可以输出 PWM 信号数值的中间值
Max当前通道可以输出 PWM信号数值的最大值

### 2.6 故障保护
![image](https://github.com/wzezhong/Rover/blob/master/images/%E6%95%85%E9%9A%9C%E4%BF%9D%E6%8A%A4%E8%B0%83%E8%AF%95.JPG)
在故障保护界面， 左边的一列显示的是遥控器的输入， 右边一列显示电机输出， 显示的是飞控的 I/O 输出的信号，不用连接电机, 在该界面也可以看到飞控的输出是否正常（在解锁模式下，拨动遥控器的摇杆会有输出显示）
![image](https://github.com/wzezhong/Rover/blob/master/images/%E6%95%85%E9%9A%9C%E4%BF%9D%E6%8A%A4%E8%B0%83%E8%AF%951%E4%BF%A1%E9%81%93.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E6%95%85%E9%9A%9C%E4%BF%9D%E6%8A%A4%E8%B0%83%E8%AF%952.JPG)

## 三 设置参数
### 3.1 全部参数列表
点击 CONFIG/TUNNING进入调试界面， 然后会发现没有高级参数和全部参数等项，点击 Planner 然后按照图中所示，下拉选择 Advanced. 选择之后会发现没什么变化，然后我们需要切换到其他界面，例如切换到 FLIGHT DATA界面，之后再点击 CONFIG/TUNNING, 会发现左侧列表如下图所示
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%85%8D%E7%BD%AE%E8%B0%83%E8%AF%95%E4%B9%8B%E6%89%93%E5%BC%80%E5%85%A8%E9%83%A8%E5%8F%82%E6%95%B0.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%85%8D%E7%BD%AE%E8%B0%83%E8%AF%95%E4%B9%8B%E9%AB%98%E7%BA%A7%E5%8F%82%E6%95%B0.JPG)
点击 Full Parameter List， 如下图所示， 点击OK
![image](https://github.com/wzezhong/Rover/blob/master/images/%E9%85%8D%E7%BD%AE%E8%B0%83%E8%AF%95%E4%B9%8B%E5%85%A8%E9%83%A8%E5%8F%82%E6%95%B0%E8%A1%A8.JPG)
由上图可以看出全部参数列表中的布局
1， 第一列是各种参数（命令）的名称
2， 第二列是参数的设置值
3， 第三列是参数的单位
4， 第四列是参数的值可以选择那些参数。只有在选项里面的参数才是有意义的。
5， 第五列是参数的含义，作用描述。

### 3.2 设置输出通道
设置目标：1号输出通道控制左边电机；3号输出通道控制右边电机。
搜索servo1，找到SERVO1_FUNCTION参数，默认值是26。在我们的无人车上使用，并且是差速转向，那么，这个值应该设置成73. 在后面的列表中有相对应的解释
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%AE%BE%E7%BD%AE%E8%BE%93%E5%87%BA%E9%80%9A%E9%81%93%E5%87%BD%E6%95%B01.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%AE%BE%E7%BD%AE.JPG)
搜索servo3，找到SERVO3_FUNCTION参数，默认值是70。在我们的无人车上使用，并且是差速转向，这个值应该设置成74
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%AE%BE%E7%BD%AE%E8%BE%93%E5%87%BA%E9%80%9A%E9%81%93%E5%87%BD%E6%95%B03.JPG)
#### 注意： 直接在表中值的那一列，键入所需要的值就好。每次设置完所有的参数后，点击 Write Params 按钮，飞控可能会提示重启飞控，重启飞控就好。重启飞控会重新刷写飞控内存中的数据，如果写入参数后，飞控没有按照的意愿动作，那么可以重启飞控再看看效果—将飞控彻底断电后再重新供电
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%AE%BE%E7%BD%AE%E9%80%9A%E9%81%93%E5%87%BD%E6%95%B0%E4%B9%8B%E5%86%99%E5%85%A5%E5%8F%82%E6%95%B0.JPG)

### 3.3 解锁参数设置
arm_checks 是解锁检查. 这里面涉及到的传感器参数全部设置好了，才可以解锁. Arm_require 是解锁的必要条件，比如说油门拉到最小值从而设置解锁的动作
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E5%8F%82%E6%95%B0%E8%AE%BE%E7%BD%AE1.JPG)
因为我在室内调试无人车，所以没有GPS的信号，因此飞控无法解锁. 但是我们的无人车速度并不快，所以为了调试的方便，把这两个值设为0
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E5%8F%82%E6%95%B0%E8%AE%BE%E7%BD%AE2.JPG)
紧接着，搜索 safe，然后找到参数 BRD_SAFETYENABLE, 该参数用来设置是否使用安全开关
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E5%8F%82%E6%95%B0%E8%AE%BE%E7%BD%AE3.JPG)
把参数改为0， 点击 Write Params
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E5%8F%82%E6%95%B0%E8%AE%BE%E7%BD%AE4.JPG)
当我们完成写入参数的任务后，我们需要重新启动飞控，然后我们回到 FLIGHT DATA界面，可以看到已经解锁成功.

## 四 解锁
### 4.1 确认解锁
我们重新回到 INITIAL SETUP界面，会发现如图所示为解锁成功。
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E6%88%90%E5%8A%9F1.JPG)

### 4.2 解锁检查验证
此时，为了验证我们是否成功解锁，我们可以拨动遥控杆，看电机的输出是否有变化，如果产生相对应的变化，则证明解锁成功，上图所示可以明显看到信道3加大，右边的电机输出增加，为测试所有的操作是否正确，我进行了以下测试，拨动不同的遥杆看对应的电机输出是否有变化
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E6%88%90%E5%8A%9F2.JPG)
![image](https://github.com/wzezhong/Rover/blob/master/images/%E8%A7%A3%E9%94%81%E6%88%90%E5%8A%9F3.JPG)
至此，完成了小车的所有校准工作和小车运行起来的所有工作

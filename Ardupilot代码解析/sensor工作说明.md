## 流程
1. drive level -> 2. sensor level -> 3. EFK level -> 4. Reading level

## 详细工作流程
1. 获取陀螺仪的数据，采用定时回调函数进行自动采集
2. 采集数据之后进行积分
3. 积分之后在sensor.cpp里面会根据积分时间进行平均计算->得到角速度
4. 使用get_best函数，从几组陀螺仪数据里面选出最好的一组数据，之后发布在sensor_combine里面

## 分层说明---sensor level(Reference)
在sensor.cpp中有陀螺仪，加速度计，气压和空速等传感器的值，这个函数对所有的传感器的原始值进行了滤波，然后发布。发布在sensor_combine主题里面，供其他函数调用。这个sensors.cpp里面关键的几个函数  
// _voted_sensors_update.sensors_poll(raw)  
这个函数在拉取数据的同时，对数据进行了滤波，滤波就是上面提到的那个注释，其实这里还做了一个事情，就是机体坐标系的调整，也就是你的飞控在飞机里面的安装方向的问题。然后调用了下面的函数，选出几组传感器里面最好的数据。

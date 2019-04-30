## eclipse端口被占用的问题

### cmd 执行 netstat -ano|findstr "8080"  (对应端口号)
### 得到了进程号“13384”； PID
### tasklist|findstr "13384"，得到进程映像名javaw.exe；

#### 1、任务管理器->详细信息标签->找到对应的PID，右键点击结束进程，端口恢复
#### 2、kill掉这个进程 CMD>taskkill /F /PID 13384

### 重新启动项目，端口被占用的问题应该是OK了
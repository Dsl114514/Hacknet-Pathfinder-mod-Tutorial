# **高级Executables功能的实现**  

## *将这些放在 LoadContent() 中*
### *检测Proxy(代理)是否开启*
```
  Computer computer = Programs.getComputer(os, os.thisComputer.ip);
  if (computer.proxyActive)
  {
      os.write("Error: Proxy is not enabled!");
      needsremoved = true;
      return;
  }
```
> **computer.proxyActive 检查Proxy（代理）**  
> **os.write 在游戏控制台显示一句话**  
> **needsremoved = true 立即关闭程序**  

### **检查目标计算机是否开发特点端口**
```
if (!computer.isPortOpen(computer.GetDisplayPortNumberFromCodePort(Port number))){
      os.write("Error: SSH port is not open!");
      needsremoved = true;
      return;
  }
```
> **Port number 填入的端口号**
### 打开防火墙
```
computer.firewall.solved = true;
```
### 执行命令
```
os.execute("Commands");
```
> **Commands** 填入游戏中的命令  

### [动画]()

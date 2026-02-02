# 端口
## 游戏端口列表
```
ssh 22
ftp 21
smtp 25
web 80
sql 1433
medical 104
torrent 6881
ssl 443
pacific 192
rtsp 554
transfer 211
version 9418
blizzard 3724
eos 3659
sigscramble 32
```
## 注册端口
```
Pathfinder.Port.PortManager.RegisterPort("vnc", "Virtual Network Console", 5900);
```
> ***第一个参数 填写协议的缩写（只能小写,用于端口映射）***  
> ***第二个参数 填写协议的全称***  
> ***第三个参数 填写默认端口号（可选，如果没有定义请在xml中设定）***  

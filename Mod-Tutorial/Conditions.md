# 命令
* ***创建一个新命令***
```
public static void TestCommand(OS os, string[] args)
{
    os.write("Arguments passed in: " + string.Join(" ", args));
}
```
> * **在该静态方法中填入一些功能** 
* ***注册***  
在Mod主文件的Load()中使用
```
Pathfinder.Command.CommandManager.RegisterCommand("CommandName", TestCommand);
```
***进行注册***
> ***CommandName*** 命令的名称，在游戏中输入的指令  
> ***TestCommand*** 命令调用的静态方法

* ***示例***
```
public static void TestCommand(OS os, string[] args)
{
    string ip = os.connectedIP;
    os.write("ip：" + ip + string.Join(" ", args));
}
```
> ***该示例读取当前连接的ip并通过os.write在游戏控制台打印它***

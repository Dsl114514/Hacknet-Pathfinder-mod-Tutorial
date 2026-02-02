# **Executables (可执行文件)**

## ***基本的可执行程序***
为什么要调用这么多命名空间呢？  
因为少个using多找一次bug 导致红温（你也可以按自己的需求删除pwp）。

```
using BepInEx;
using BepInEx;
using HarmonyLib;
using Hacknet;
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Graphics;
using Pathfinder.Action;
using Pathfinder.Administrator;
using Pathfinder.Util;
using Pathfinder.Daemon;
using Pathfinder.GUI;
using Pathfinder.Mission;
using Pathfinder.Util.XML;
using System;
using System.IO;
using System.Collections.Generic;
using Pathfinder;
using Hacknet.Extensions;
using BepInEx.Hacknet;
using System.Diagnostics;
public class BasicExecutable : Pathfinder.Executable.BaseExecutable
{
    public BasicExecutable(Rectangle location, OS operatingSystem, string[] args) : base(location, operatingSystem, args) {
        this.ramCost = 761;
        this.IdentifierName = "ExecName";
    }

    public override void LoadContent()
    {
        base.LoadContent();
    }

    public override void Draw(float t)
    {
        base.Draw(t);
        drawTarget();
        drawOutline();
    }

    private float lifetime = 0f;
    public override void Update(float t)
    {
        base.Update(t);
        lifetime += t;
    }
}
```

> ramCost 程序占有的内存
>
> IdentifierName 程序RaM栏显示的名称
>
> LoadContent(){} 首次执行后触发的内容
>
> Draw(float t){} 程序的主窗口，可以在里面绘制动画
>
> Update(float t){} 循环触发（每帧）
>
> isExiting = true 关闭程序

* ***打开端口*** 
```
Programs.getComputer(os, targetIP).openPort("Port", os.thisComputer.ip);
```
 
> Port 填入对应的端口协议，可在 [端口页](Ports.md) 查看详情  
> targetIP 玩家在执行Executables时连接的 IP  
> thisComputer 玩家电脑

* ***注册***    

* *在mod主文件的Load()里注册*
```
Pathfinder.Executable.ExecutableManager.RegisterExecutable<BasicExecutable>("#PF_BASIC_EXE#");
```
* *属性注册*
```
[Pathfinder.Meta.Load.Executable("#PF_BASIC_EXE#")]
```
> #PF_BASIC_EXE# 为在xml里调用的方法 如下
```
<file path="bin" name="Crack.exe">#PF_BASIC_EXE#</file>
```
* ***退出***  

* 实例
```
private float lifetime = 0f;
public override void Update(float t)
{
    base.Update(t);
    lifetime += t;
    if (lifetime > 2.5f)
        isExiting = true;
}
```
***
***当lifetime大于2.5秒关闭程序***
```
if (lifetime > 2.5f)
        isExiting = true;
```
***
## [高级]()

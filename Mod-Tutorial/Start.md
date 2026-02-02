# 开始
* 如下C#代码  
```
using BepInEx;
using BepInEx.Hacknet;

namespace HacknetPluginTemplate
{
    [BepInPlugin(ModGUID, ModName, ModVer)]
    public class HacknetPluginTemplate : HacknetPlugin
    {
        public const string ModGUID = "com.Windows10CE.Template";
        public const string ModName = "MOD NAME HERE";
        public const string ModVer = "1.0.0";

        public override bool Load()
        {
            return true;
        }
    }
}
```
* ModGUID 
> Mod的唯一标识符
* ModName 
> Mod的名称
* ModVer 
> Mod的版本号（只能是数字）
* Load（）
> 用于"注册"Mod的 Executables,Actions等

  

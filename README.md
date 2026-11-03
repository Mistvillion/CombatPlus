# CombatPlus

《空洞骑士：丝之歌》的战斗节奏增强 mod。它让敌人出招更快、前后摇更短、站立和发呆的时间更少，战斗因此更紧凑、更难。

- 动作速度（1~10 倍）：敌人的攻击动画、前后摇、移动和跳跃整体加快，位移距离不变。
- 停顿缩短（1~10 倍）：敌人站立、发呆以及两次出招之间的停顿时间变短。

登场和死亡演出、受击硬直、被击退的过程以及投射物不受影响。改动只对之后出现的敌人生效，出图再进即可看到效果。

## 安装

前置插件：[BepInEx 5](https://github.com/BepInEx/BepInEx/releases)（5.4.23 或更高的 5.x，Windows x64版）

1. 把 BepInEx 5 的压缩包解压到游戏根目录，也就是 `Hollow Knight Silksong.exe` 所在的文件夹。
2. 启动一次游戏再退出，BepInEx 会生成 `BepInEx\plugins`、`BepInEx\config` 等目录。
3. 把本仓库的 `BepInEx` 文件夹复制到游戏根目录，合并进去。最终应得到：
   ```
   Hollow Knight Silksong\BepInEx\plugins\CombatPlus\CombatPlus.dll
   ```
4. 启动游戏。如果 `BepInEx\LogOutput.log` 里出现 `CombatPlus ... loaded`，说明安装成功。

### 高级：可选安装

安装 [BepInEx.ConfigurationManager](https://github.com/BepInEx/BepInEx.ConfigurationManager/releases)（**BepInEx5** 版） 

按 F1 打开通用设置菜单，可以改高级设置：按敌人单独设置倍率、在日志中打印敌人名字、修改设置面板的按键。不装也完全能用，高级设置可以直接编辑配置文件。

安装方法：把它压缩包里的 `BepInEx` 文件夹合并到游戏根目录。

## 使用

游戏中按  F2 打开 CombatPlus 设置面板。所有设置都保存在 `BepInEx\config\com.combatplus.silksong.cfg`。

### 高级：按敌人单独设置

在配置文件的 `PerEnemy` 项（或 F1 菜单的高级设置）中填写：

```
名字=动作速度,停顿缩短
```

## 卸载

删除 `BepInEx\plugins\CombatPlus` 文件夹即可。如果想清理干净，也可以一并删除 `BepInEx\config\com.combatplus.silksong.cfg`。

## 已知问题

- 倍率很高（例如 5 倍以上）时，个别敌人可能出现穿墙、卡进地形或动作异常。遇到时请调低倍率，或用“按敌人单独设置”只调低那一个敌人。
- 敌人的加速、减速过程，以及少数不走物理引擎的位移，不会随倍率变快。
- “登场、演出、硬直不加速”是根据敌人状态名判断的，个别敌人可能误判。

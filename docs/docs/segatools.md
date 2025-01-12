---
comments: true
---

# SEGATOOLS 常见配置项目

!!! warning "观看前必读"

    本文档系对 [TeamTofuShop/segatools](https://gitea.tendokyu.moe/TeamTofuShop/segatools) 的配置文档进行翻译并附带笔者个人理解的产物。

    文档说明可能会因为笔者的理解能力而产生误差。
    
    如果您对文档内容有疑问，欢迎访问[原文链接](https://gitea.tendokyu.moe/TeamTofuShop/segatools/src/branch/develop/doc/config/common.md)或下方评论区讨论！

!!! info "TASOLLER (抬手乐) / TASOLLER PLUS (抬手乐普拉斯) / ZhouSensor (大四) 用户必读"

    如果您使用的控制器为TASOLLER（抬手乐）/TASOLLER PLUS（抬手乐普拉斯）/ZhouSensor（大四）的其中一种或者几种，请使用 fufubot 版本的 Segatools！

该文档描述了适用于所有游戏的 Segatools 配置设置。

键盘绑定设置使用[虚拟键代码](https://learn.microsoft.com/zh-cn/windows/win32/inputdev/virtual-key-codes)。
 ---

## **配置路径**

配置文件的默认文件路径是`./segatools.ini`。

您可以将变量`SEGATOOLS_CONFIG_PATH`修改为其他路径。

例如，您有另一个start.bat包含以下代码的目录，然后您可以复制segatools.ini到其中，another_config.ini但其中包含不同的 DNS 服务器

``` ini
set SEGATOOLS_CONFIG_PATH=.\another_config.ini
```

---

## **[aimeio]**

控制 Aime 读卡器组件的模拟。

!!! note ""

    ### **`enable`**

    默认：`1`

    启用 Aime 读卡器组件模拟。禁用则使用原生 SEGA Aime 读卡器（COM 端口号因游戏而异）。

!!! note ""

    ### **`portNo`**

    默认值：`游戏特定`

    设置用于 Aime 卡读卡器组件的 COM 端口。

!!! note ""

    ### **`highBaud`**

    默认：`1`

    将 Aime 读卡器的波特率设为 115200（而不是 38400）。某些游戏（例如 CHUNITHM）需要此功能，但其他游戏（例如 WACCA）则不需要此功能。

!!! note ""

    ### **`gen`**

    默认：`1`

    生成 Aime 读卡器的型号信息，这也会改变为游戏提供的 LED 信息。

    1: TN32MSEC003S H/W 版本 3.0 / TN32MSEC003S F/W 版本 1.2

    2：837-15286 / 94

    3：837-15396 / 94

!!! note ""

    ### **`aimePath`**

    默认：`DEVICE\aime.txt`

    包含 Aime 卡ID的文本文件的路径。

    !!! warning "注意"

        Aime 卡ID为20位阿拉伯数字。

!!! note ""

    ### **`aimeGen`**

    默认：`1`

    如果文件 aimePath 不存在，是否生成随机 Aime 卡ID。

!!! note ""

    ### **`felicaPath`**

    默认：`DEVICE\felica.txt`

    包含 FeliCa 电子现金卡 IDm 序列号的文本文件的路径。

!!! note ""

    ### **`felicaGen`**

    默认：`0`

    如果文件 felicaPath 不存在，是否生成随机 FeliCa ID。

!!! note ""

    ### **`scan`**

    默认：`0x0D`（VK_RETURN）

    虚拟键代码。如果按住此按钮，则模拟 IC 卡读取器将模拟其附近的 IC 卡。可以模拟各种不同的 IC 卡；模拟的卡的具体选择取决于配置的卡 ID 文件是否存在。
# AimeIO 方式连接游戏

## 食用须知
AimeIO 依托于 Segatools 对读卡器的 hook，可以实现游戏内读卡器热插拔<br>但是受限于 Segatools，有以下缺点：
* 使用`Amusement IC`卡片时**无法登录 SEGA 官服**；
* 目前无法读取卡号**非 510 开头**的版本的`Banapass`：
  * 日本发行的旧版（非`Amusement IC`版本的）
  * 在海外发行的所有版本，包括国行
* 部分 Segatools 无法使用包括`Amusement IC`在内的所有 [Felica](https://zh.wikipedia.org/wiki/FeliCa) 卡片，如果您出现了刷 `Amusement IC`, `Hime` 等 Felica 卡片时游戏中遇到了刷卡错误的情况，请更换一份Segatools，或者更换为串口协议连接

**标准版需求固件版本号 ≥ `2024083100` （2024 年 8 月 31 日后发货的可以直接用**

**Lite 版需求固件版本 ≥ `2024090500`（2024 年 9 月 5 日后发货的可以直接用**

## 游戏配置
1. 首先请确保你的游戏是**已经联网**的，进入游戏后能够显示一个**绿色地球图标**，否则请先把游戏的联网设置好，不在本文讨论范围内
2. 把本文提供的`hinata.dll`放入游戏目录下<br>[点我下载](https://github.com/nerimoe/HINATA-release/releases/download/HINATA-2024090500/hinata.dll)（如果下载慢的话可以在售后群下载）
3. 打开`segatools.ini`，并按照如下方式修改：
   ```ini
   ;如果没有[aime]条目则请手动添加该条目和条目下内容
   [aime]
   enable=1
   ;enable=1的用途是启用segatools的读卡器hook，也可以什么都不加，如果什么都不加的话默认是启用的

   ;如果没有[aimeio]条目的话需要自己添加
   [aimeio]
   path=hinata.dll
   brightness=128
   ;path用于指定dll路径
   ;brightness控制读卡器亮度 0 ~ 255可选，如果不加的话默认为128
   ```
4. 启动游戏
5. 部分 Segatools 无法使用包括`Amusement IC`在内的所有 [Felica](https://zh.wikipedia.org/wiki/FeliCa) 卡片，如果您出现了刷 `Amusement IC`, `Hime` 等 Felica 卡片时游戏中遇到了刷卡错误的情况，请更换一份Segatools，或者更换为串口协议连接


## 其他页面
* [串口方式连接 SEGA 游戏](serial.md)
* [游戏内测试读卡器](in_game_test.md)
* [KONAMI 游戏设置](../KONAMI/index.md)
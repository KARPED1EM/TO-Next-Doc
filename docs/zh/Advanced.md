---
lang: zh-CN
title: 进阶教程
---

# 进阶教程

## 快捷键

| 快捷键                                             | 功能                   | 权限                 |
| -------------------------------------------------- | ---------------------- | -------------------- |
| <kbd>F11</kbd>                                     | 切换分辨率             | 模组端               |
| <kbd>Alt</kbd> + <kbd>Enter</kbd>                  | 切换全屏/窗口          | PC端                 |
| <kbd>F5</kbd> + <kbd>T</kbd>                       | 重新加载翻译文件       | 模组端               |
| <kbd>F5</kbd> + <kbd>X</kbd>                       | 导出翻译文件           | 模组端               |
| <kbd>Ctrl</kbd> + <kbd>F1</kbd>                    | 输出日志至桌面         | 模组端               |
| <kbd>Alt</kbd> + <kbd>C</kbd>                      | 复制当前当前设置       | 模组端               |
| <kbd>F10</kbd>                                     | 打开游戏目录           | 模组端               |
| <kbd>Ctrl</kbd>+<kbd>鼠标右键</kbd>                | 处决选中的玩家         | 房主&会议中          |
| <kbd>Shift</kbd> + <kbd>C</kbd> + <kbd>Enter</kbd> | 强制显示聊天按钮       | 房主&游戏中          |
| <kbd>Shift</kbd> + <kbd>L</kbd> + <kbd>Enter</kbd> | 强制结束游戏           | 房主&游戏中          |
| <kbd>Shift</kbd> + <kbd>M</kbd> + <kbd>Enter</kbd> | 强制召开/跳过会议      | 房主&游戏中          |
| <kbd>Shift</kbd>                                   | 立即开始游戏           | 房主&开始游戏倒计时  |
| <kbd>C</kbd>                                       | 重置开始游戏倒计时     | 房主&开始游戏倒计时  |
| <kbd>Shift</kbd> + <kbd>Ctrl</kbd>+ <kbd>N</kbd>   | 显示当前游戏设置的说明 | 房主                 |
| <kbd>Ctrl</kbd>+ <kbd>N</kbd>                      | 显示当前游戏设置       | 房主                 |
| <kbd>Ctrl</kbd>+ <kbd>Delete</kbd>                 | 恢复TOHE默认设置       | 房主&大厅中          |
| <kbd>Shift</kbd> + <kbd>E</kbd> + <kbd>Enter</kbd> | 自杀                   | 房主&游戏中          |
| <kbd>Shift</kbd> + <kbd>D</kbd> + <kbd>Enter</kbd> | 打开飞艇的所有门       | 房主&调试模式&游戏中 |
| <kbd>Shift</kbd> + <kbd>K</kbd> + <kbd>Enter</kbd> | 将击杀冷却设置为0秒    | 房主&调试模式&游戏中 |
| <kbd>Shift</kbd> + <kbd>T</kbd> + <kbd>Enter</kbd> | 完成所有任务           | 房主&调试模式&游戏中 |
| <kbd>Y</kbd>                                       | 向所有客户端同步RPC    | 房主&调试模式&游戏中 |
| <kbd>G</kbd>                                       | 展示开场动画           | 房主&调试模式&游戏中 |
| <kbd>=</kbd>                                       | 切换任务显示状态       | 房主&调试模式&游戏中 |
| <kbd>I</kbd>                                       | 获取当前坐标           | 房主&调试模式&游戏中 |

## 聊天框指令

| 指令            | 功能                              | 权限   |
| --------------- | --------------------------------- | ------ |
| /dump           | 输出日志至桌面                    | 模组   |
| /v              | 查看所有玩家的模组版本            | 模组   |
| /win            | 显示上局游戏获胜玩家              | 所有人 |
| /l              | 显示上局游戏结果                  | 所有人 |
| /rn [名字]      | 修改自己的名字                    | 房主   |
| /hn [房间号]    | 覆盖房间号                        | 房主   |
| /level [等级]   | 修改自己的游戏等级                | 房主   |
| /n              | 显示当前游戏设置                  | 所有人 |
| /n r            | 显示所有开启的职业                | 所有人 |
| /r              | 显示所有开启的职业                | 所有人 |
| /r [职业]       | 显示指定职业的介绍                | 所有人 |
| /dis [crew/imp] | 以【船员/内鬼】断连为结果结束游戏 | 房主   |
| /h              | 显示所有指令帮助                  | 所有人 |
| /m              | 显示自己职业的介绍                | 所有人 |
| /t [模板]       | 显示模板文本                      | 模组端 |
| /mw [秒]        | 修改消息发送间隔限制              | 房主   |
| /s [内容]       | 发送房主消息                      | 房主   |
| /exe [玩家ID]   | 处决指定的玩家                    | 房主   |
| /kill [玩家ID]  | 击杀指定的玩家                    | 房主   |
| /color [颜色]   | 修改自己的颜色                    | 所有人 |
| /qt             | 永远退出该房间                    | 所有人 |
| /xf             | 修复名字遮挡的问题                | 所有人 |
| /id             | 显示所有玩家的ID                  | 房主   |
| /qq             | 请求车队姬群发该房间的房号        | 房主   |
| /end            | 强制结束游戏                      | 房主   |
| /hy             | 强制召开/跳过会议                 | 房主   |

## 职业技能优先级

可能会有不少人对于TOHE判定职业技能冲突时会发生什么有疑问。而正好，TOHE从221版本开始重写了击杀玩家的代码逻辑，使得击杀与被杀分为两个独立的事件。

比如，呪狼击杀老兵时究竟是谁死，答案是老兵反杀呪狼，呪狼的技能不会触发。绝大部分TOHE的职业的技能不会连锁效应，除非是特别设计过。所以当呪狼击杀老兵时触发了老兵的技能，则老兵反杀呪狼。以上，呪狼击杀老兵视为 `击杀事件`，老兵反杀呪狼视为 `被杀事件`，至此两事件已经达成并判定完成，`击杀事件` 与 `被杀事件` 最多只能各存在一次，因此不会继续触发一个新的 `被杀事件` 以触发呪狼反杀老兵。

再比如，处刑人的目标是小丑，若小丑被票出视为谁的胜利？根据原本程序的判定由于小丑比处刑人更早出现在模组，因此小丑的胜利判定更优先。但我们在职业介绍中特别注明了 `小丑、处刑人、冤罪师可以共享胜利`，所以答案是一起获胜。也就是说，除了特别说明的职业，一般技能发动优先是根据职业更新顺序的。

根据上一条，吸血鬼吸血鹈鹕，然后鹈鹕吞下吸血鬼，若此时开启会议，鹈鹕和吸血鬼谁死？因为吸血鬼很早就有了，而鹈鹕是后来新增的职业，因此吸血鬼的判定优先于鹈鹕，所以答案是鹈鹕死。此外，若这个会议是鹈鹕召开的则会议不会召开，因为鹈鹕此时已经死亡。那么如果没有开会鹈鹕还会因为吸血鬼吸血而死吗？其实所有延迟类技能都是另外一个事件，并不与其它事件冲突，所以最后鹈鹕会因吸血而死，吸血鬼也会得到拯救。

顺带说个有趣的，时间操控者已经完成了3个任务，会议时间增加了45秒。若此时时间操控者叛变，那么会议时间不会增加而是减少45秒。因为他的技能判定是在会议时间计算时统一判断的而不是累计的。值得一提的是，很多类似累计类型的职业技能都是统一在需要时判断而不是一次次累加并记录。这样可以减少计算量也不需要对变量进行繁琐的操作。例如集票者的票数是在投票时统一计算在场有多少玩家是被集票者击杀，而不是集票者每次击杀都会储存一次票数。宝箱怪也是同理。

## 修改欢迎&会议提示信息

首先打开您游戏的根目录，找到 `..\Among Us\TOHE_DATA\template.txt` 文件

可以看到该文件内有 `welcome` 、`OnMeeting` 等字样，其中 `welcome` 就是其他玩家进入您的房间时会发送的消息，`OnMeeting` 则是每次会议开始会发送的消息。其中 `\n` 是换行的意思。虽然我们完全允许您随意修改这些文件，但请尽量不要修改该文件的格式，以避免不必要的游戏错误。

## 修改封禁名单&违禁词&违禁昵称

首先打开您游戏的根目录 `..\Among Us\TOHE_DATA\`

在此目录可以看到四个文件，请打开文件并按照原格式修改，每行对应一个，如需添加更多请换行。

- BanList.txt  -  封禁玩家（好友代码）
- BanWords.txt  -  违禁词（请在游戏内开启【踢出使用违禁词的玩家】选项以生效）
- DenyName.txt  -  违禁昵称
- template.txt  -  消息模板（[上一条](#修改欢迎-会议提示信息)）
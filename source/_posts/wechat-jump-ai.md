---
title: 用JavaScript玩微信跳一跳(iOS版)
tags: []
categories: []
date: 2018-01-02 21:57:55
---

在Python版 https://zhuanlan.zhihu.com/p/32452473 的基础上用NodeJS重新实现了所有代码，并优化了棋子识别的逻辑。

#### 实现原理:
通过WebDeviceAgent截取手机游戏图片，识别棋子和方块的位置，计算两者距离，算出按压屏幕的时间。

#### 所需工具：
Xcode
iOS手机
NodeJS
#### 操作步骤：
安装WebDeviceAgent，可以参考 iOS 真机如何安装WebDriverAgent
从https://github.com/jianggaocheng/wechat_jump_game_node.git拉取代码
执行npm install安装依赖组件
运行安装好的 WebDriverAgentRunner
将手机点击到《跳一跳》小程序界面
命令行运行 node iOS_Ai.js
#### FAQ:

1 每次跳跃的位置都不在中心（跳不准）

调整代码中config.json中pressCoefficient的数值，想跳近些就调小，反之调大
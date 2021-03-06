# 4 游戏的总体设计

经过上一章的需求分析工作，已经确定了本游戏的各方面需求，接下来对游戏的总体设计方向进行概述，划分并设计游戏的功能模块。

## 4.1 游戏总体技术方案

由图4–1可了解整体的技术路线。UnrealEngine4游戏引擎，是在操作系统下进行运行的。蓝图通过调用由UnrealEngine4引擎使用C++封装的节点，来实现不同的游戏功能。

图4–1“极速跑酷”游戏的技术路线图

## 4.2 游戏功能模块的划分

上述的总体方案从整体上分析了本游戏需要用到的技术支持。根据之前的分析结果，考虑本游戏进行时的呈现的功能不同，还需要划分出进行游戏所需的主要功能模块，以便于高效地完成以后的详细分析工作 为极速跑酷的总体功能模块图。

图4–2极速跑酷游戏的模块设计方案

根据图4-2，我们划分类总体的功能模块，对以上模块我们需要进行更加详细的设计与分析。各个模块的功能设计如下：

\(1\)界面实现

该模块负责在游戏操作运行时，人与机器的交互。将不同的控件显示在屏幕上，响应用户的点击操作，并触发事件。以供用户进行游戏操作。

\(2\)声效实现

通过对游戏不同位置添加声音实现音效。

\(3\)人物控制

该模块实现人物的动画播放，通过不同的触发事件，播放相应的人物动画，该部分是游戏的核心部分。

\(4\)关卡的创建

该部分实现场景的无限循环。通过不断的进行物品的创建和销毁，来使场景无限的进行循环。

\(5\)宠物伴随

该模块实现了人工智能的部分，增加了游戏的趣味性，同时也是核心部分。宠物是伴随人物进行运动的。

\(6\)物品创建

该模块实现了障碍物以及物品的创建，游戏通过触发碰撞的方式来随机产生新的物品和障碍物。

## 4.3 本章小结

本章的主要内容是对本课题进行总体设计，制定了总体设计方案，列举出了本游戏的核心技术问题，然后围绕这些问题细分出了本游戏的重要功能模块，并对各个功能模块进行了逐一设计。


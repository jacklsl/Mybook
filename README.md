基于UnrealEngine的“极速跑酷”

游戏的设计与实现

Design and Implementation of The SpeedParkour

Game Base on UnrealEngine

基于UnrealEngine的“极速跑酷”

游戏的设计与实现

\[摘 要\] 伴随着互联网和硬件设备的发展，游戏的种类越来越多样化，游戏的趣味性越来越好，特别是在虚拟现实技术的兴起使得游戏的开发进入一个全新的阶段。本文以UnrealEngine4为游戏引擎，采用蓝图和UnrealEngine4的游戏框架等技术，设计和开发了一款“极速跑酷”2D的跨平台游戏。用户可以通过两个按钮能够控制和操作游戏中的人物动作、吃掉物品，得到分数等，同时该游戏采用卡通式的风格。游戏在制作过程中，充分考虑内存问题，使得游戏可以很好的运行。

\[关键词\] 虚幻4引擎 ；虚拟现实；蓝图；跨平台游戏

Design and Implementation of The SpeedParkour

Game Base on UnrealEngine

**Abstract: **Along with the development of Internet and hardware equipment, games are becoming more and more diversified and interesting, especially with the rise of virtual reality technology, it brings the game development into a new stage. In this paper, it takes UnrealEngine4 as the game engine and completes a game of "Speed Parkour" which is an cross platform 2D game by using blueprint and UnrealEngine4's game framework. Users can operate character movement, control the person to eat items and get scores through tow buttons. The game uses cartoon style and considers the memory problem, so that the game can be a good run in the production process.

**Key words: **UnrealEngine4；virtual reality；blueprint；cross platform game

# 

# 

# 

# 

# 

# 6 游戏实现

到此为止，本游戏的设计工作已基本完成。根据本游戏所需的开发环境，本章将先对游戏开发前需做的一些准备工作进行阐述，然后再按照第六章的设计思路，描述对游戏中的类及各个功能模块的具体实现过程。

## 6.1 游戏开发前准备工作

在为 Android 开发前，我们首先要安装 Android SDK，该 SDK 为发布到 android 提供开发所需的程序和代码，下面来介绍如何安装该软件。

如果您是从 GitHub 下载的虚幻 4，那再运行 Android Works 的安装文件前您需要先完成以下步骤。 并且以下步骤对下载虚幻 4 的源码版本，无论是 Windows 还是 Mac 的电脑，都是适用的。 如果您是通过启动器下载的预编译版本，那么久可以跳过这个步骤，直接开始安装 Android Works。

当虚幻 4 从 Github 上下载并解压后，运行文件 Setup.bat 来下载其他所需要的文件，其中包含 Android Works 的安装文件。

在 Setup.bat 运行完成后，找到 Android Works 的安装文件，并跟随下面的说明。

如果已经安装安卓 SDK，但丢失了环境变量，则可跳过以下所有步骤，只需使用编辑器中的 Edit Menu -&gt; Project Settings -&gt; Android SDK 属性指向安装位置。

\(1\)导航到 TADP 安装文件夹：

表6-1 TADP 安装文件夹

| 安装类型 | 位置 |
| --- | --- |
| 二进制 | \[EngineInstallLocation\]\Unreal Engine\[EngineVersion\]\Engine\Extras\Android |
| GitHub | \[EngineSyncLocation\UE4\Engine\Extras\Android |

如果您是从 GitHub 下载的虚幻 4，那再运行 Android Works 的安装文件前您需要先完成以下步骤。 并且以下步骤对下载虚幻 4 的源码版本，无论是 Windows 还是 Mac 的电脑，都是适用的。 如果您是通过启动器下载的预编译版本，那么久可以跳过这个步骤，直接开始安装 Android Works。

当虚幻 4 从 Github 上下载并解压后，运行文件 Setup.bat 来下载其他所需要的文件，其中包含 Android Works 的安装文件。

在 Setup.bat 运行完成后，找到 Android Works 的安装文件，并跟随下面的说明。

\(2\) Double-click AndroidWorks-1R1-windows.exe。

\(3\)单击Next。

\(4\)单击Next。

\(5\)选择一个文件夹来下载并安装 Android Works，并在完成后单击 Next 按钮。

\(6\)确认您要安装的是 AndroidWorks1R1 并点击 Next。

\(7\) 点击单选框，对授权协议没有异议的话选择 Accept All，并单击 Accept 按钮。

\(8\) 会弹出一个新窗口，显示 Android Works 工具下载和安装的进度。

\(9\) 当所有的工具都下载安装完成后，在接下来的窗口中点击 OK 继续安装进程。

\(10\) 这时可以点击 Finish 来完成 Android Works 的安装。

\(11\)最后，点击 Yes 重启电脑。

## 6.2 游戏中类的实现

根据游戏的设计，可将游戏游戏负责游戏功能的主要类做出如下的实现。

\(1\) 界面类的父类均是 UserWidget类，这些类实现游戏主要界面的显示和逻辑处理功能。这些类包括：登录界面；主界面；设置界面；完成界面等，他们各自实现了不同的功能。

\(2\) 人物类的父类是Pawn类，这些类实现类接收玩家的输入，并作出相应的动作。

人物类主要实现了，一段跳，二段跳，跑步等动作。

\(3\) 物品类的父类是Actor类，这些类实现了物品的移动和物品的排布方式。

## 6.3 游戏记时的实现

游戏通过获取GameTimeinSeconds节点获取初始化时的时间，通过TimeLeft的值与GameTimeinSeconds的值相加得到StartTime就是倒计时时间。

图6-1类的初始化

游戏通过tick事件获取分钟和秒的时间。

图6-2类的时间的获取和显示

## 6.4 游戏核心程序的实现

游戏核心程序包括了：人物程序，宠物程序，关卡程序。

人物程序主要控制人物的动作。通过游戏界面的“滑动”按钮和“跳跃”按钮。控制人物的滑动，一段跳和二段跳。宠物程序主要控制宠物的伴随。通过不同状态，改变伴随状态。关卡程序主要负责创建游戏的关卡，负责游戏的循环场景。

### 6.4.1 人物程序的实现

如图6-3所示，人物的控制是通过战斗界面的点击，进行实现人物的一段跳和二段跳以及侧滑。点击“跳跃”控制人物的。游戏通过输入事件进行事件的触发。

玩家通过控制“跳跃”按钮实现人物的一段跳和二段跳。

图6-3人物程序跳跃的实现

如图6-4所示，玩家通过按下“滑动”按钮人物实现滑动，释放“滑动”按钮人物恢复奔跑。

图6-4人物程序滑动的实现

### 6.4.2 宠物程序的实现

如图6-5所示，程序通过Tick事件获取不同状态下的位置通过Lerp节点改变宠物位置。

图6-5宠物伴随的实现

### 6.4.3 关卡程序的实现

如图6-6所示，程序通过触发事件进行关卡的创建。当碰撞器碰撞，获取对方组件名为“End”时，在碰撞的位置，通过Select节点随机产生新的物品。

图6-6关卡创建的实现

## 6.5 游戏其他功能的实现

如图6-7所示，战斗界面的“滑动”按钮按下事件，被触发后，通过获取游戏人物，调用人物的滑动事件。

图6-7战斗界面的“滑动”按钮按下事件实现

如图6-8所示，战斗界面的“滑动”按钮释放事件，被触发后，通过获取游戏人物，调用人物的跑步事件。

图6-8战斗界面的“滑动”按钮释放事件实现

如图6-9所示，战斗界面的“跳跃”按钮事件，被触发后，通过获取游戏人物，调用人物的跳跃事件。

图6-9斗界面的“跳跃”按钮事件实现

如图6-10所示，战斗界面的“暂停”按钮事件，被触发后，通过SetGamePaused节点暂停游戏，再次被触发，游戏继续。

图6-10战斗界面的“暂停”按钮事件实现

## 6.6 本章小结

本章内容主要介绍了本游戏的实现过程。首先简述了游戏开发前所需要做的准备工作。接着是本章的重点内容，根据上一章的设计要领，阐述了游戏中的主要类和各个功能模块的实现，最后概述了游戏中的其他功能的实现过程。


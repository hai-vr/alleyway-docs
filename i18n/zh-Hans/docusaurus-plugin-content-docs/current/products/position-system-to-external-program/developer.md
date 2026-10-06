---
sidebar_position: 150
title: 开发者文档
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 开发者文档

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

本网站的大部分文档面向的是应用程序的用户。

如果你是开发者，应查阅 [GitHub 上的 README.md](https://github.com/hai-vr/position-system-to-external-program/)，
以获取有关提取过程、着色器、WebSocket API 以及摄像机位置提取的技术信息。

## 为其他机械臂添加支持 {/* #adding-support-for-other-robotic-arms */}

你是想连接一款尚未支持的机械臂的开发者吗？[请查看 GitHub](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` 中的 [**Submit()** 函数](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)可能是一个不错的切入点。

## WebSocket {/* #websockets */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

如果你在使用 *Resonite*，或者在修改 *ChilloutVR*，又或者在开发基于 Basis 框架的应用程序，
你可能应该使用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

在软件的 *Data calibration* 标签页底部的 *Resonite WebSockets* 部分，勾选复选框以启用 WebSocket 服务。

![position-system_CUz03IfbdR.png](@site/docs/products/position-system-to-external-program/img/position-system_CUz03IfbdR.png)

你可以在[这里找到 WebSocket 消息规范](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)：

> 如果启用了 *WebSocket* 支持，我们会在端口 **56247** 上开放一个 WebSocket，地址为 `ws://localhost:56247/ws`
> 
> 向其发送以下字符串，表示已解析的位置和法线：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ
> ```
> - *PositionX*、*PositionY*、*PositionZ* 是本地空间中的位置，其中 (0, 0, 0) 是最底部的中心，(0, 1, 0) 是最顶部的中心。
> - *NormalX*、*NormalY*、*NormalZ* 是方向，用长度为 1 的向量表示。即使你没有将其长度设为 1 也没关系，我们无论如何都会对其进行归一化。
> 
> 顺便一提，你还可以提交切线，它可用于定义扭转，但这是可选的：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ TangentX TangentY TangentZ
> ```
> - *TangentX*、*TangentY*、*TangentZ* 是切线（一个与方向垂直的向量），用长度为 1 的向量表示。即使你没有将其长度设为 1 也没关系，我们无论如何都会对其进行归一化。

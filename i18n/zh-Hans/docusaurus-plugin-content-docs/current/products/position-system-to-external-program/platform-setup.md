---
sidebar_position: 30
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 设置头像

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
只有**连接**机械臂的**电脑**需要安装软件和预制件。虚拟空间中的其他用户不需要，
他们只需要一个标准的类 DPS 灯光。

如果他们已经有标准的类 DPS 灯光（例如 SPS），就可以直接控制你的机械臂，无需进行任何额外设置。
:::

请根据你的平台或应用程序，选择以下其中一个部分：
- [使用 Modular Avatar 的 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-modular-avatar)
- [使用 VRCFury 的 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-vrcfury)
- [**Resonite**](#resonite)
- [**ChilloutVR**](#chilloutvr)
- [使用 **Basis** 框架构建的应用程序](#applications-built-using-the-basis-framework)

## 使用 Modular Avatar 的 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-modular-avatar */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::info
如果你有 Modular Avatar，推荐使用此方法。如果你没有 Modular Avatar，但有 VRCFury，[请参阅下方的另一部分](#vrchat-avatars-sdk-using-vrcfury)。<br/>
**你必须至少拥有这两者之一。**

*另外，SPS 灯光也是类 DPS 灯光。它们可以与此位置系统配合使用。*
:::

在头像中：
- 在 *Project* 标签页中，打开 *Packages/Alleyway - Position System/Prefabs/* 文件夹。
- 将 *PositionSystem-VRC-MA* 预制件添加到你的头像根部。

![Unity_vBn2gPNKzq.png](@site/docs/products/position-system-to-external-program/img/Unity_vBn2gPNKzq.png)

你可以进一步自定义设置，以下步骤为可选：
- 你可以缩放 *System* 对象。黄色杆的长度大致相当于机械臂的总行程。
- 如果你想更改菜单位置，`(prefab)/System` 中有一个 *MA Menu Installer* 组件。
- 默认情况下，校准原点位于右手。
    - 你可以使用位于 `(prefab)/System/HandRoot` 的 *Armature Link* 组件将其切换到左手。
    - 应该将其设为惯用手还是非惯用手并没有明确答案。我个人将其设置在惯用手上。
    - 其子对象 *HandPalmDown* 会悬浮在你的手掌下方，距离手部大约两只手的距离。

如果你使用会合并网格的头像优化工具，请排除此对象：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 这个网格很特殊，不得被转换或简化。

## 使用 VRCFury 的 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-vrcfury */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::note
我自己的项目不使用 VRCFury，对它的组件也不够熟悉。尽管如此，我还是参照 Modular Avatar 预制件，
使用等效的组件尝试制作了 VRCFury 预制件。

但是，我无法保证 VRCFury 预制件的设置是正确的。

*另外，SPS 灯光也是类 DPS 灯光。它们可以与此位置系统配合使用。*
:::

在头像中：
- 在 *Project* 标签页中，打开 *Packages/Alleyway - Position System/Prefabs/* 文件夹。
- 将 *PositionSystem-VRC-VRCFury* 预制件添加到你的头像根部。

![5bbBMWuP85.png](@site/docs/products/position-system-to-external-program/img/5bbBMWuP85.png)

你可以进一步自定义设置，以下步骤为可选：
- 你可以缩放 *System* 对象。黄色杆的长度大致相当于机械臂的总行程。
- 如果你想更改菜单位置，`(prefab)/System` 中有一个 *Full Controller* 组件。
- 默认情况下，校准原点位于右手。
    - 你可以使用位于 `(prefab)/System/HandRoot` 的 *Armature Link* 组件将其切换到左手。
    - 应该将其设为惯用手还是非惯用手并没有明确答案。我个人将其设置在惯用手上。
    - 其子对象 *HandPalmDown* 会悬浮在你的手掌下方，距离手部大约两只手的距离。

如果你使用会合并网格的头像优化工具，请排除此对象：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 这个网格很特殊，不得被转换或简化。

## VRChat Worlds SDK {/* #vrchat-worlds-sdk */}

:::danger
🚫 **我们不建议将着色器数据编码系统集成到世界中。**

这是因为用户可能需要自定义着色器材质，以修复头显内的对齐问题。
:::

目前不支持世界。不过，请考虑以下几点：

类 DPS 灯光并不局限于头像。如果你希望由世界来控制机械臂，或许可以
使用相同的类 DPS 灯光设置。

此外，我们支持 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)；
如果你在为自己制作世界，也可以编写一个向 WebSocket 提交命令的日志解析器。

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

Resonite 支持 WebSocket，可用于提取位置和法线。

在一个对象中创建 *WebsocketClient* 组件。使用 *Websocket Text Message Sender* 节点发送文本消息。
- 我们会在端口 **56247** 上开放一个 WebSocket，地址为 `ws://localhost:56247/ws`
- 文本消息字符串的格式需要符合 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system) 文档中的规定。
- 传入给定坐标空间中的位置（例如本地变换或全局变换）。
- 传入与位置处于同一坐标空间的方向（例如 Up 或 Forward 方向之类）。
- *你也可以选择传入一个切线（例如 Up 或 Forward 方向之类），它应与方向垂直。我们目前尚未使用该信息，但将来可能会用它来控制扭转。*

使用软件时，[你需要启用 WebSocket 服务，因为它默认是关闭的](developer#websockets)。

目前我们没有提供可直接使用的 ProtoFlux 物品。请参考下图了解一种可行的实现方式。

:::note
既然你在读这段内容，你对 ProtoFlux 的了解可能比我更深，所以如果你发现这张蓝图中有明显错误，
请不要照搬。

例如，这应该只在连接机械臂的电脑上运行，但这张图目前并没有加以限制。
:::

[![resonite_websocket.jpg](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)

## ChilloutVR {/* #chilloutvr */}

<HaiTags>
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

:::danger
将 ChilloutVR 预制件添加到头像上有些困难，你需要将你的基础动画控制器与我们的动画控制器合并，
而我不知道如何干净利落地完成这一步。

可能会出现问题，所以如果你要尝试，请做好心理准备。
:::

已尝试性地添加了一个预制件。

- 在 *Project* 标签页中，打开 *Packages/Alleyway - Position System/Prefabs/* 文件夹。
- 将 *PositionSystem-ChilloutVR* 预制件添加到你的头像根部。
- 它**必须**位于头像根部。**不要重命名**预制件对象。动画依赖于它。

![Unity_XEqPy4mBCe.png](@site/docs/products/position-system-to-external-program/img/Unity_XEqPy4mBCe.png)

如果你想解包预制件：
- 解包预制件。
- 将 HandRoot 和 NeckRoot 对象分别移动到你的手部骨骼和颈部骨骼。
  - 应该将 HandRoot 分配给惯用手还是非惯用手并没有明确答案。我个人将其设置在惯用手上。
  - 其子对象 *HandPalmDown* 会悬浮在你的手掌下方，距离手部大约两只手的距离。
- 将它们的本地位置设为零。

:::note
如果你想在不解包预制件的情况下完成此操作，请改为执行以下步骤：
- 将 HandRoot 和 NeckRoot 对象的**副本**分别创建到你的手部骨骼和颈部骨骼上。
  - 应该将 HandRoot 分配给惯用手还是非惯用手并没有明确答案。我个人将其设置在惯用手上。
  - 其子对象 *HandPalmDown* 会悬浮在你的手掌下方，距离手部大约两只手的距离。
- 将它们的本地位置设为零。
- 在预制件中，找到 `(prefab)/System/CalibrationConstraint`。
- 在 *Position Constraint* 组件中，将约束源重新指定为你新的 HandRoot 对象。
- 在 *Aim Constraint* 组件中，将约束源重新指定为你新的 NeckRoot 对象。
:::

设置你的动画控制器：
- 在 Project 视图中，进入 `Packages/Alleyway - Position System/Internal/App-ChilloutVR/AbsolutePaths/`
- 打开 `PositionSystem-Animator-CVR-Absolute.controller` 动画控制器资源文件，
- 将其中的两个层复制到你自己的动画控制器中，包括参数和参数的值 **（TODO：这要怎么做？？？）**。

设置你的 *CVR Avatar* 组件：
- 在 Advanced Settings 中：
  - 添加一个名为 *Enabled* 的 Float 类型 Toggle，用于切换参数 `PStoEP_Enabled`
  - 添加一个名为 *Enabled and Visible* 的 Float 类型 Toggle，用于切换参数 `PStoEP_EnabledAndVisible`
  - 添加一个名为 *Bring to Hand* 的 Float 类型 Toggle，用于切换参数 `PStoEP_BringToHand`

可选：
- 你可以缩放 *System* 对象。黄色杆的长度大致相当于机械臂的总行程。

:::info[面向 ChilloutVR 高级用户的补充信息]

以下内容可以帮助你了解如何转换这个预制件。

对象结构：
- 将 `(prefab)/System/HandRoot` 重新设为你其中一只手的子对象，这只手将用于校准原点。
    - 应该将其设为惯用手还是非惯用手并没有明确答案。我个人将其设置在惯用手上。
    - 其子对象 *HandPalmDown* 会悬浮在你的手掌下方，距离手部大约两只手的距离。
- 将 `(prefab)/System/NeckRoot` 重新设为你颈部骨骼的子对象。

组件操作/动画：
- 使用该着色器的编码器网格只需对拥有连接机械臂的电脑的人可见（头像穿戴者，
  或生成该物品的用户）。
- 有一些约束已被转换为 Unity 系统，并附带相应的动画。ChilloutVR 中的动画逻辑有所不同，因为它使用的是世界对象预制件技巧。

如果你可以修改 ChilloutVR，也可以考虑使用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。
:::

## 使用 Basis 框架构建的应用程序 {/* #applications-built-using-the-basis-framework */}

<HaiTags>
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

由于 Basis 项目允许修改，最简单的方法是**不**使用通过屏幕像素进行的数据提取。

请改用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

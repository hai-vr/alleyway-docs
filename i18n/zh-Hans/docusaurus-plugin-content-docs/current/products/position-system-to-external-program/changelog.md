---
title: 更新日志
sidebar_position: 100
---
import HaiLocalization from "/src/components/HaiLocalization";

# Position System to External Program - 更新日志

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

---

## 1.2.0

- 🌃 *预制件和着色器没有变化。*
- 🖥️ *程序已更新。*

添加模拟扭转：
- 由于类 DPS 数据只包含位置和方向信息，缺少这部分信息，我们无法实现真正的“扭转”。
- 添加了根据横向位置和横滚得出的模拟扭转。
- 在 Robotics 标签页的设置中，添加了 Twist 部分来配置此模拟扭转。

尝试修复设备使用蓝牙串口通信时出现的问题：
- 添加了一个限制每秒更新次数的新设置，位于界面中新的 *Wireless* 标签页。

*与 1.2.0-alpha.2 相比：仅在勾选复选框时才显示速率限制滑块。*

## 1.2.0-alpha.2

- 🌃 *预制件和着色器没有变化。*
- 🖥️ *程序已更新。*

尝试修复设备使用蓝牙串口通信时出现的问题：
- 添加了一个限制每秒更新次数的新设置，位于界面中新的 *Wireless* 标签页。

## 1.2.0-alpha.1

- 🌃 *预制件和着色器没有变化。*
- 🖥️ *程序已更新。*

添加模拟扭转：
- 由于类 DPS 数据只包含位置和方向信息，缺少这部分信息，我们无法实现真正的“扭转”。
- 添加了根据横向位置和横滚得出的模拟扭转。
- 在 Robotics 标签页的设置中，添加了 Twist 部分来配置此模拟扭转。

## 1.1.0

- 🌃 *预制件和着色器没有变化。*
- 🖥️ *程序已更新。*

添加最小高度硬限位：
- 这可防止机械臂低于特定高度，从而限制其运动范围。
- 勾选 *Compensate virtual scale* 时，虚拟缩放会在内部得到补偿，**并且**会应用一个偏移，
  使得在硬限位之间的范围内移动时，仍然需要在虚拟空间中走完全部行程。

## 1.0.2

- 🌃 *预制件和着色器没有变化。*
- 🌃 *程序没有变化。*

此版本中没有会影响到你的更改。

`package.json` 已更新为新的描述，该描述将显示在列表聚合器中。

## 1.0.1

- 🌃 *预制件和着色器没有变化。*
- 🖥️ *程序已更新。*

修复：在带有使整个画面变暗的后期处理的世界中，数据解码不再失败。
- 修复：在“for Two”世界中，校验和不再失败。

---

## 1.0.0

正式发布。

*源代码与 1.0.0-beta.1 完全相同，只是使用新的版本号重新构建。*

---

## 1.0.0-beta.1

- 🌃 *VRChat 预制件和着色器没有变化。*
- 🌕 *ChilloutVR 预制件已更改。应使用最新版本重新上传头像，以便使用部分功能。*

在编译后的程序文件中包含许可证，并在软件中添加了 README.txt 文件。

为公开发布准备软件。

其他：
- 将默认的 VR 坐标从 (0, 0) 更改为 (1, 1)。

修复：
- 从 ChilloutVR 预制件中移除了 Animator 组件。
- 修复：ChilloutVR 约束因在 Unity 2022 中保存而无法在 Unity 2021 中工作的问题。
- 修复：Rotate machine 无法立即更新的问题。
- 让预览模型不那么令人困惑。

---

## 0.2.0-beta.1

💥 *重大变更：安装此新包之前，需要先移除旧包。资源 GUID 不变。部分预制件名称有变化。*

🌕 *预制件已更改。应使用最新版本重新上传头像，以便使用部分功能。*

**此版本包含重大变更。**

包名已缩短为 `dev.hai-vr.alleyway.position-system`。这意味着在安装此包之前，你必须先卸载旧包。

资源 GUID 不变，但部分预制件名称已更改。

由于该产品尚未正式宣布发布，因此主版本号不变。

### 添加 ChilloutVR 预制件基础 {/* #add-chilloutvr-prefab-base */}

ChilloutVR 的安装步骤[记录在此处](./platform-setup#chilloutvr)。

### 其他 {/* #other */}

重大变更：
- 重大变更：包名已缩短为 dev.hai-vr.alleyway.position-system。
- 重大变更：重命名预制件以缩短其名称。
- 重大变更：在预制件中，缩短了网格编码器的名称。
- 重大变更：将 ChilloutVR 和 VRChat 的资源分到不同的文件夹中。
- 重大变更：重命名了许多资源并将其移动到不同的文件夹中。
- 由于对象名称发生了变化：
  - 重新生成了 ChilloutVR 绝对路径动画。
  - 重新生成了 VRChat 相对路径动画。

其他：
- 添加了一个预览网格，帮助用户根据头像身高来缩放系统。
- 将菜单放入一个子菜单中。
- 菜单现在带有图标。
- GitHub Releases 现在会包含一个 .unitypackage 文件。

---

## 0.1.0-beta.7

🌃 *Unity 预制件和着色器没有变化。*

### 添加 ChilloutVR 预制件基础 {/* #add-chilloutvr-prefab-base-1 */}

ChilloutVR 的安装步骤[记录在此处](./platform-setup#chilloutvr)。

### 其他 {/* #other-1 */}

- GitHub Releases 现在会包含一个 .unitypackage 文件。

---

## 0.1.0-beta.6

🌕 *Unity 着色器已更改。应使用最新版本重新上传头像，以便使用部分功能。*

### 新功能：添加最大高度硬限位选项。 {/* #new-feature-add-a-maximum-height-hard-limit-option */}

硬限位会降低机械臂被允许移动的最大高度。

更改此值时，虚拟缩放会在内部进行补偿，使得在硬限位之间的范围内移动时，仍然需要在虚拟空间中走完全部行程。
可以通过 Compensate virtual scale 复选框禁用此功能。

### 新功能：添加偏移俯仰选项。 {/* #new-feature-add-an-offset-pitch-option */}

偏移可让你在应用位置后调整机械臂的俯仰角。

这不会改变移动的方向。虚拟空间中的移动在物理空间中仍会是相同的方向。

### 新功能：添加整体旋转机械臂的设置。 {/* #new-feature-add-a-setting-to-rotate-the-robotic-arm-entirely */}

使用 Rotate machine 设置时，虚拟空间中朝某一方向的移动，会在物理空间中变为另一个方向的移动。

- 这可以将虚拟空间中的水平运动转换为物理空间中的垂直运动。
- 另外，如果你使用的是水平放置的机械臂，使用此设置可以校正空间，使虚拟空间与物理空间一致。

### 添加 VRCFury 预制件 {/* #add-vrcfury-prefab */}

VRCFury 的安装步骤[记录在此处](./platform-setup#vrchat-avatars-sdk-using-vrcfury)。

### 其他 {/* #other-2 */}

修复：
- 现在会忽略不可见的窗口，因此搜索窗口名称应该会更快。
- 编码器网格上不再带有已删除的 Animation 组件（网格资源绑定的“Animation Type”现在设为 None）。

其他：
- **根 PID 控制器不稳定，因此在此版本中已被禁用。**
- 校准器小工具模型的材质已从 lilToon 切换为 Standard，以避免安装预制件时需要 lilToon。
- 由于不再需要过多考虑泛光效果，改回使用灰色像素而不是红色像素。着色器版本已更改为 V1.0.1 以反映这一点。
- 由于 WebSocket 不仅可用于 Resonite，所有提及 Resonite WebSockets 的地方都已改为 WebSockets。
- 在 Debug 菜单中，提供虚拟与物理之间缩放差异的估算值。这是为将来的工作做准备，以便在摄像机因在虚拟空间中移动而开始移动时，
  在游玩空间中重新定位对象。

---

## 0.1.0-beta.5

🌃 *Unity 预制件和着色器没有变化。*

修复：现在无需在电脑上安装 ASP.NET Core 运行时也能启动应用程序。
- 在不使用 AspNetCore 的情况下重新实现了 WebSocket 服务。

---

## 0.1.0-beta.4

🌕 *Unity 着色器已更改。应使用最新版本重新上传头像，以便使用部分功能。*

### 新功能：将世界空间中的摄像机位置和旋转添加到数据中。 {/* #new-feature-add-world-space-camera-position-and-rotation-to-the-data */}

世界空间中的摄像机位置和旋转现在会被编码到数据中。
此项新增的目的是提供另一种将 SteamVR 叠加层固定在世界空间中的方式。

着色器版本已更新为 V1.1.0。

修复：
- 修复：WebSocket 的法线现在会被归一化。

---

## 0.1.0-beta.3

🌃 *Unity 预制件和着色器没有变化。*

### 新功能：添加可选的 WebSocket 服务以支持 Resonite。 {/* #new-feature-add-optional-websocket-service-for-resonite-support */}

现在可以从 *Resonite* 向 WebSocket 发送位置和法线来控制机械臂。
由于所发送的位置实际上模拟的是同样的类 DPS 灯光，因此机械臂的运动仍受 Robotics 标签页中设置的约束。

如果收到任何有效消息，它将覆盖所有数据提取逻辑；不会再进行任何图像或数据处理。

更多详情，请参阅 [README.md 中的 *Websockets as an alternative input system* 部分](https://github.com/hai-vr/position-system-to-external-program?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

---

## 0.1.0-beta.2

🌃 *Unity 预制件和着色器没有变化。*

### 新功能：添加 PID 控制器以稳定机械臂。 {/* #new-feature-add-pid-controllers-to-stabilize-the-robotic-arm */}

Robotics 标签页现在提供一个自动调整根位置的 PID 控制器选项，
以及另一个用于对目标位置进行阻尼的 PID 控制器。

### 新功能：添加限制横向轴的安全设置。 {/* #new-feature-add-safety-setting-to-clamp-the-lateral-axes */}

Robotics 标签页现在提供一个将横向移动限制在圆内的安全模式。
圆在最底部时比在最顶部时更小。

### 新功能：添加自定义虚拟缩放设置。 {/* #new-feature-add-custom-virtual-scale-setting */}

Robotics 标签页现在提供用于更改虚拟世界缩放的滑块。
值越大，意味着需要在虚拟空间中移动更多，才能在物理空间中产生同样的移动量。

### 其他 {/* #other-3 */}

修复：
- 修复：任一坐标为负数时 OpenVR 提取器崩溃的问题。
- 默认情况下，在窗口和 VR 都未打开时，界面不再显示 *Data is OK*。

其他：
- 如果目标与根之间的距离大于 3，则忽略输入数据。
- 从应用文件夹名称中移除了波浪号。
- 将 zip 文件名更改为 position-system。

---

## 0.1.0-beta.1

### 新功能：将标准类 DPS 灯光的位置连接到机械臂。 {/* #new-feature-connect-the-position-of-standard-dps-like-lights-to-a-robotic-arm */}

这是首个测试版。

此测试版包含一个可执行文件（`.exe`），它可以：
- 解码通过 OpenVR 纹理传输的类 DPS 数据。
- 解码通过窗口传输的类 DPS 数据。
- 将类 DPS 数据提交到连接着使用 Tcode 协议（SR6 和 OSR2 所使用）的机械臂的任意串口。

该包包含一个预制件和一个着色器：
- 预制件使用 Modular Avatar 并会创建一个菜单。其同步参数总开销为 2 位。
- 预制件不需要任何手动设置。着色器已在预制件中设置好。

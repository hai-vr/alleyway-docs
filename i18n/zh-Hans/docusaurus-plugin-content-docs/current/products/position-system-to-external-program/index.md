---
title: "Position System to External Program"
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Position System to External Program* 是一个**预制件**和一个**程序**，可让你将标准类 DPS 灯光的位置连接到机械臂。

其他用户可以通过虚拟空间远程控制你的机械臂的位置和旋转。

:::tip
只有**连接**机械臂的**电脑**需要安装软件和预制件。虚拟空间中的其他用户不需要，
他们只需要一个标准的类 DPS 灯光。

如果他们已经有标准的类 DPS 灯光（例如 SPS），就可以直接控制你的机械臂，无需进行任何额外设置。
:::

<HaiVideo src="./img/position-system-f-noaudio.mp4"></HaiVideo>

*该软件在 GitHub 上以 MIT 许可证免费开源，因此你可以对其进行审查。*

## 实现原理 {/* #how-is-it-done */}

其原理是使用一种特殊的着色器，将像素编码到窗口画面或投射到头显中的图像上。
然后由我们的程序读取这些像素。

数据提取使用的是**无害的屏幕捕获**技术，类似于窗口和 VR 直播捕获程序所使用的技术。
不会篡改任何电脑程序，也不会干预任何进程。也不使用 OSC。

此外：
- 还会提取摄像机在世界空间中的位置和旋转。这可用于将 SteamVR 叠加层固定在世界空间中。
- 还可以选择开放一个 WebSocket 服务，以便从 Resonite 等虚拟空间系统控制机械臂。

<HaiVideo src="./img/ILX73J2vHu-f.mp4"></HaiVideo>
*这种数据提取方式与屏幕捕获类似，完全无害。*

## 兼容的机械臂 {/* #compatible-arms */}

目前，已知该软件可与以下机械臂配合使用：

| 厂商          | 型号    | 协议       | 通信方式 | 备注                                                                                  |
|-------------|-------|----------|------|:------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 串口   |                                                                                     |
| Tempest MAx | SR6   | T-code   | 串口   | ⚠️ 请务必阅读：<br/>[修补 SR6 固件](./firmware-patches#patching-the-sr6-firmware-file) |

:::info
如果你的设备不在上表中，请[查看常见问题](./other)。

由于目前没有拥有此类设备的开发贡献者，因此暂不支持无线连接。不过，
至少有一位 OSR2+ 用户使用自定义固件成功实现了 *Serial over Bluetooth*，所以无线连接完全是可行的。

如果你是开发者，[或许可以提供帮助](other#my-robotic-arm-is-not-in-that-list-how-to-add-it)。
:::

<HaiVideo src="./img/resonite-position-system-f.mp4"></HaiVideo>
*在 Resonite 中，数据通过 WebSocket 传输，而不是通过图像数据提取。*

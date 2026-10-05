---
sidebar_position: 80
---
import HaiLocalization from "/src/components/HaiLocalization";

# 常见问题

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

### 程序的配置文件保存在哪里？ {/* #where-are-the-program-config-files-saved */}

配置文件保存在 `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` 文件夹中。

### 目前哪些机械臂设备可以使用？ {/* #what-robotic-arm-devices-are-currently-working */}

目前，已知该软件可与以下机械臂配合使用：

| 厂商          | 型号    | 协议       | 通信方式 | 备注                                                                                  |
|-------------|-------|----------|------|:------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 串口   |                                                                                     |
| Tempest MAx | SR6   | T-code   | 串口   | ⚠️ 请务必阅读：<br/>[修补 SR6 固件](./firmware-patches#patching-the-sr6-firmware-file) |

由于目前没有拥有此类设备的开发贡献者，因此暂不支持无线连接。不过，
至少有一位 OSR2+ 用户使用自定义固件成功实现了 *Serial over Bluetooth*，所以无线连接完全是可行的。

其他支持 T-code 协议的机械臂也可能受支持。

### 我的机械臂不在列表中。如何添加支持？ {/* #my-robotic-arm-is-not-in-that-list-how-to-add-it */}

如果你的设备是由 Tempest 设计的，由于他们的设备使用 T-code 协议，它很可能已经可以使用。
我没有测试过这一点。

否则，你需要其他开发者的帮助才能做到这一点。
我自己无法为其他设备添加支持，因为我不太可能拥有其他类似的机械臂。

如果你认识愿意尝试添加支持的开发者，[请让他们查看 GitHub](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` 中的 [**Submit()** 函数](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)可能是一个不错的切入点。

如果你的设备只有一个运动轴，将来或许可以添加与 *Intiface* 的集成。

### 无线：机械臂出现卡顿，或运动不流畅 {/* #wireless-the-robotic-arm-is-stuttering-or-it-is-not-smooth */}

至少有一位用户报告过机械臂异常卡顿的情况，而该用户使用的是
无线通信（通过蓝牙进行的串口通信）。结果发现，问题很可能是由电脑造成的
某种无线干扰。

如果你使用的是无线设备，请尝试将蓝牙适配器发射器接到 USB 延长线上，
使其远离电脑。

### 无线速率限制 {/* #wireless-rate-limiting */}

如果你正在开发无线模块，或者正在使用通过蓝牙进行串口通信的特殊固件，
你可能需要、也可能不需要减少每秒发送到设备的更新次数。

界面中的 Wireless 标签页可让你更改更新速率。默认情况下，更新速率为每秒 100 次。

对于无线设备，较低的值（例如每秒 20 次更新）可能更为合理。

### 软件的旧版本 {/* #older-versions-of-the-software */}

[安装](./install)页面只提供软件和预制件最新版本的链接。

如需旧版本，请查看 [GitHub 发布页面](https://github.com/hai-vr/position-system-to-external-program/releases)。

所有发布版本和可执行文件都是由 GitHub 的自动化基础设施直接使用存储库的源代码编译而成的。

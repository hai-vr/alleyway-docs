---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 首次校准

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

首次启动程序时，你需要进行设置以确认其能正常工作。

## 启动程序 {/* #start-the-program */}

如果你尚未安装，请下载 .NET 7.0 Runtime 的“Run console apps” https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

然后，启动 `position-system.exe`。

:::note
如果你想使用 WebSocket，请查看[开发者文档页面](./developer#websockets)
:::

## VR 校准 {/* #vr-calibration */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} /><HaiTag requiresSteamVR={true} />
</HaiTags>

:::warning
这需要 SteamVR。如果你不使用 SteamVR，则需要使用窗口校准。

*如果你是 OpenXR 开发者，[或许可以提供帮助](https://github.com/hai-vr/position-system-to-external-program/issues/1)。我还没有时间研究这个问题。*
:::

在实际操作之前，你应该先完整阅读以下说明。

以下校准操作需要查看一个窗口来确认是否正常工作。但是，窗口的内容取决于你在 VR 中看到的画面。
**打开 SteamVR 桌面窗口会遮挡整个屏幕**并导致投影问题。你不能用 SteamVR 桌面窗口来确认是否正常工作。

对于首次校准，我建议将头显抬起，使其暂时架在额头上，然后查看实际显示器屏幕上的窗口。
下次就不需要再这样做了。

- 在软件中，切换到 *Data calibration* 标签页。
- 如果你还没有进入 VR，请以 VR 模式启动你选择的游戏，并加载你已设置好的头像或物品。
- 你应该处于 VR 中，因为我们需要确保头显纹理已被校准。
- 打开游戏内菜单，然后：
  - 将 **Enable** 切换为开启。
  - 按住 **Bring to Hand** 按钮，一秒后松开。
- 如果一切顺利，你应该会在 *Data calibration* 标签页上看到一条像素带。

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

如果显示的不是这样，或者红色显示 **Checksum is failing** 消息，那么：
- 确保你的 SteamVR 菜单没有打开。
- 点击 + 和 - 按钮来移动像素。
- 查看[下一页以进行进一步的故障排除](./fix-calibration-errors)。

## 替代方案：窗口校准 {/* #alternative-window-calibration */}

:::warning
窗口校准可以使用，但不推荐，因为游戏很可能需要额外渲染一个摄像机；
此外，在某些情况下，使用摄像机可能会被视为侵犯隐私。
:::

除了使用 SteamVR，你也可以使用窗口校准。
- **如果 SteamVR 对你有效，请不要这样做。**
- 在 *Data calibration* 中，将 Extractor preference 更改为 *PrioritizeWindow*。
- 在 *Window name* 字段中，输入窗口名称的开头部分。
  - 错误：如果我们的程序未能检测到正确的窗口，你可能需要重新启动应用程序。这将在以后的版本中修复。
- *如果你使用 VRChat 并处于 VR 中，请将摄像机切换为 Stream 摄像机。*

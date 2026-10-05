---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 安装

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
只有**连接**机械臂的**电脑**需要安装软件和预制件。虚拟空间中的其他用户不需要，
他们只需要一个标准的类 DPS 灯光。

如果他们已经有标准的类 DPS 灯光（例如 SPS），就可以直接控制你的机械臂，无需进行任何额外设置。
:::

## 下载软件 {/* #download-software */}

可以在以下位置下载软件：

- 下载 **[1.2.0 软件 (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/position-system-1.2.0-executable.zip)**

如果你尚未安装，请下载 .NET 7.0 Runtime 的“Run console apps” https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

*如果你是开发者，可以[在 GitHub 上审查软件源代码](https://github.com/hai-vr/position-system-to-external-program/)。*

## 下载预制件 {/* #download-prefab */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

下载预制件的方法：
- 将 **Alleyway [ALCOM 存储库](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** 添加到你的存储库中。
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- 将 *Alleyway - Position System to External Program* 包添加到你的项目中。

或者，你也可以在这里获取 .unitypackage 文件：

- 下载 **[1.2.0 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/dev.hai-vr.alleyway.position-system-1.2.0.unitypackage)**

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

目前还没有可供下载的 .resonitepackage。请阅读[头像设置文档，了解一种可行的 ProtoFlux 设置方式](./platform-setup#resonite)。

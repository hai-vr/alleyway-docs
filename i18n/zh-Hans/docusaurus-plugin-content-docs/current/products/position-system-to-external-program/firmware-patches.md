---
sidebar_position: 200
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 修补 SR6 固件

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

## 修补 SR6 固件文件 {/* #patching-the-sr6-firmware-file */}

如果你使用 SR6，可能需要修补固件以防止某个错误发生。

:::info
以下内容仅适用于使用 SR6 机械臂的情况。
:::

### 补丁 {/* #patch */}

在 `SR6-Alpha5_ESP32.ino` 的第 429 行，`SetPitchServo` 函数中，将以下这行：

```c
  float beta = acos((csq + 5625 - bsq)/(150*c)); // Angle between c-line and servo arm
```

替换为：

```c
  float beta = acos(constrain((csq + 5625 - bsq)/(150*c), -1, 1)); // Angle between c-line and servo arm
```

然后，按照 SR6 的使用说明书将固件上传到你的设备。

### 原因 {/* #reason */}

在开发本软件的过程中，我们发现该固件存在一个错误，会导致向舵机发送无效的数值。

当机械臂被指令移动到一个不寻常的位置时，就会发生这个错误，而在虚拟空间中，这样的位置是实际可能达到的。

这个错误的指令会使舵机做出错误的响应，移动到一个极端位置。

因此，如果你使用 SR6，我建议你修补固件。

<HaiVideo src="./img/firmware-f.mp4" autoWidth={false} halfWidth={true}></HaiVideo>

:::note
技术原因：一个大于 1 的值（例如 1.153）被传入了 `acos` 函数。这会返回 NaN。

这可能表明固件中的逆运动学求解器存在错误。
:::

---
sidebar_position: 5
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# ⚠️ 安全警告

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

通常，家用机械臂传统上是由生成平滑曲线的数学算法来控制的。
这使它们的运动非常可预测、易于测试，并能确保机械臂的运动舒适，且相对不会出现杂乱无章的动作。

然而，**本软件并非如此**。机械臂不是由数学算法控制，而是由一个共享的虚拟空间控制，
而这是一个不完善的系统。

通过共享虚拟空间使用位置系统时，**机械臂的运动将无法获得这些安全保障**。
请仔细考虑以下风险：
- 如果控制你的机械臂位置的实体或人员发生追踪丢失，机械臂可能会将这种追踪丢失当作一个要到达的位置。
- 如果控制你的机械臂位置的实体或人员移动过快，机械臂可能会尝试以超出电机能力的速度到达该位置：
  在这种情况下，部分电机会比其他电机早得多地到达最终位置。
  这会导致机械臂在移动过程中出现意料之外的角度。你的设备自由度越多，就越容易发生这种情况。
- 此外，固件和硬件将会处于传统软件可能认为不寻常的位置，因此这些位置可能较少经过测试。
  这些不寻常的位置可能会损坏你的机械臂，或暴露出可能影响机械臂预期位置的固件缺陷。

如果你选择在共享虚拟环境中使用机械臂，请负起责任，并**充分沟通，以确保各方都能获得更安全的体验**。

**你需对自己的人身安全承担全部责任。**

## ⚠️ 火灾隐患

一些劣质舵机可能会烧毁并发生短路，导致机械臂的部分部件发热，温度甚至可能超过
某些 3D 打印材料的玻璃化转变温度。这可能会带来火灾隐患。

请留意你的设备，并**在不使用时关闭电源**。不要在设备仍通电时入睡。

:::danger
如果你打算自己制作机械臂，**不要购买任何廉价的 20kg/cm 劣质红色舵机**。它们以容易烧毁而臭名昭著。

![servo_burn.jpg](@site/docs/products/position-system-to-external-program/img/servo_burn.jpg)
:::

---
sidebar_position: 50
---
import HaiLocalization from "/src/components/HaiLocalization";

# Robotics 设置

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

Robotics 标签页中的设置可让你自定义机械臂在使用过程中的行为。

根据你正在进行的操作，你可能需要实时调整这些设置。

## Virtual scale {/* #virtual-scale */}

*Virtual scale* 用于更改在虚拟空间中需要多少移动量才能在物理空间中产生相同的移动量，默认值为 1。

如果你使用预制件，缩放值 1 相当于从底面起算的竖直杆的高度。

![hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png)
![hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png)

> 值为 0.5 时，你需要在虚拟空间中移动一半的高度，才能在物理空间中移动全部高度：
> 
> ![hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png)

> 值为 2 时，你需要在虚拟空间中移动两倍的高度，才能在物理空间中移动全部高度：
>
> ![hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png)
> ![hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png)

:::tip
降低该值后，机械臂在物理空间中走完全部高度时，你在虚拟空间中所需付出的身体动作会更少。
:::

## Hard limits {/* #hard-limits */}

*Hard limits* 会**缩小机械臂被允许移动的最大和最小高度**。

更改此值时，Virtual scale 和偏移会在内部进行补偿，使得在 Hard limits 之间的范围内移动时，仍然需要在虚拟空间中走完
全部行程。可以通过 *Compensate virtual scale* 复选框禁用此功能。

![hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png)

:::tip
如果你觉得机械臂移动得太高，建议降低最大高度。
另一种做法是将机械臂的固定点在物理上移低，然后提高最小高度。

如果你的机械臂过早触底，你可以在物理上调整机械臂的固定点使其更高，或者提高最小高度。
:::

## Offsets {/* #offsets */}

*Offsets* 可让你在应用位置后调整机械臂的俯仰角。

这不会改变移动的方向。虚拟空间中的移动在物理空间中仍会是相同的方向。

## Safety settings {/* #safety-settings */}

:::warning
更改这些设置可能会导致机械臂出现不寻常的动作。请谨慎使用。
:::

### Limit movement at the bottom {/* #limit-movement-at-the-bottom */}

此安全设置是为能够横向移动的机械臂设计的。

*Limit movement at the bottom* 设置会执行以下操作。
- 将机械臂的横向移动限制在一个圆内。
- 当机械臂处于机器所能达到的最高高度时，该圆的半径为 100%。
- 当机械臂处于机器所能达到的最低高度时，该圆的半径为 40%。

这会将机械臂的移动限制在一个尖端朝下的截锥体形状内。

![hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png)

此设置默认开启。如果取消勾选此设置，机械臂将能够在整个范围内移动。

:::note
降低 Hard limits 时，这个锥体的形状不会被压扁，因此即使限位较低也依然安全。

![hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png)
![hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png)
:::

## Twist {/* #twist */}

如果你的设备支持扭转轴：遗憾的是，类 DPS 灯光只支持位置和方向信息；
它们没有沿方向轴的旋转信息。

这意味着我们无法实现*真正的“扭转”*。不过，你可以启用*模拟*扭转设置，
利用其他可用信息来驱动扭转电机：

- *Simulated twist from Roll* 会根据方向向侧面倾斜的程度来添加扭转。
- *Simulated twist from Lateral* 会根据位置横向偏离中心的程度来添加扭转。

滑块用于控制这些因素对扭转的影响程度。你可以设置负数，使其向相反方向扭转。

你可以同时组合使用来自 Roll 和 Lateral 的模拟扭转。

## Rotate machine {/* #rotate-machine */}

:::warning
此设置位于 **Robotics (Advanced)** 标签页中，因为它是影响最大的设置之一；
虚拟空间和物理空间的方向将不再一致。

如果你觉得机器的行为有些奇怪，请按 Reset 按钮。这会将旋转恢复为 0。
:::

使用 Rotate machine 设置时，虚拟空间中朝某一方向的移动，会在物理空间中变为另一个方向的移动。

- 这可以将虚拟空间中的水平运动转换为物理空间中的垂直运动。
- 另外，如果你使用的是水平放置的机械臂，使用此设置可以校正空间，使虚拟空间与物理空间一致。

> 值为 90 时，机器会俯仰 90 度。
> - 如果你的机械臂是竖直放置的，那么在虚拟空间中朝向你的运动，在物理空间中会变为向下的运动（空间中的方向不再一致）。
> - 如果你的机械臂是水平放置的，那么在虚拟空间中朝向你的运动，在物理空间中也会是朝向你的运动（空间中的方向一致）。
> 
> ![hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png)
> ![hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png)
> ![hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png)

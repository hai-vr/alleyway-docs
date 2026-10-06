---
sidebar_position: 50
---
import HaiLocalization from "/src/components/HaiLocalization";

# 機器人學設定

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*機器人學* 分頁中的設定可讓你自訂機械手臂在使用過程中的行為。

視你正在進行的操作而定，你可能需要即時調整這些設定。

## 虛擬比例 {/* #virtual-scale */}

*虛擬比例*用於變更在虛擬空間中需要多少移動量，才能在物理空間中產生相同的移動量，預設值為 1。

如果你使用預製物件，縮放值 1 相當於從底面起算的垂直桿高度。

![hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png)
![hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png)

> 值為 0.5 時，你需要在虛擬空間中移動一半的高度，才能在物理空間中移動全部高度：
> 
> ![hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png)

> 值為 2 時，你需要在虛擬空間中移動兩倍的高度，才能在物理空間中移動全部高度：
>
> ![hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png)
> ![hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png)

:::tip
降低此值後，機械手臂在物理空間中走完全部高度時，你在虛擬空間中所需付出的身體動作會更少。
:::

## 硬限制 {/* #hard-limits */}

*硬限制*會**縮小機械手臂被允許移動的最大和最小高度**。

變更此值時，虛擬比例和偏移會在內部進行補償，使得在硬限制之間的範圍內移動時，仍然需要在虛擬空間中走完
全部行程。可以透過 *補償虛擬比例* 核取方塊停用此功能。

![hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png)

:::tip
如果你覺得機械手臂移動得太高，建議降低最大高度。
另一種做法是將機械手臂的固定點在物理上移低，然後提高最小高度。

如果你的機械手臂太早觸底，你可以在物理上調整機械手臂的固定點使其更高，或者提高最小高度。
:::

## 偏移 {/* #offsets */}

*偏移*可讓你在套用位置後調整機械手臂的俯仰角。

這不會改變移動的方向。虛擬空間中的移動在物理空間中仍會是相同的方向。

## 安全設定 {/* #safety-settings */}

:::warning
變更這些設定可能會導致機械手臂出現不尋常的動作。請謹慎使用。
:::

### 限制底部的橫向移動 {/* #limit-movement-at-the-bottom */}

此安全設定是為能夠橫向移動的機械手臂所設計。

*限制底部的橫向移動* 設定會執行以下操作。
- 將機械手臂的橫向移動限制在一個圓內。
- 當機械手臂處於機器所能達到的最高高度時，該圓的半徑為 100%。
- 當機械手臂處於機器所能達到的最低高度時，該圓的半徑為 40%。

這會將機械手臂的移動限制在一個尖端朝下的截錐體形狀內。

![hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png)

此設定預設為開啟。如果取消勾選此設定，機械手臂將能夠在整個範圍內移動。

:::note
降低硬限制時，這個錐體的形狀不會被壓扁，因此即使限制較低也依然安全。

![hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png)
![hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png)
:::

## Twist {/* #twist */}

如果你的裝置支援扭轉軸：很遺憾，類 DPS 燈光只支援位置和方向資訊；
它們沒有沿方向軸的旋轉資訊。

這表示我們無法實現*真正的「扭轉」*。不過，你可以啟用*模擬*扭轉設定，
利用其他可用的資訊來驅動扭轉馬達：

- *Simulated twist from Roll* 會根據方向向側面傾斜的程度來加入扭轉。
- *Simulated twist from Lateral* 會根據位置橫向偏離中心的程度來加入扭轉。

滑桿用於控制這些因素對扭轉的影響程度。你可以設定負數，使其往相反方向扭轉。

你可以同時組合使用來自 Roll 和 Lateral 的模擬扭轉。

## 旋轉機器 {/* #rotate-machine */}

:::warning
此設定位於 **機器人學（進階）** 分頁中，因為它是影響最大的設定之一；
虛擬空間和物理空間的方向將不再一致。

如果你覺得機器的行為有些奇怪，請按 *重設* 按鈕。這會將旋轉恢復為 0。
:::

使用 *旋轉機器* 設定時，虛擬空間中朝某一方向的移動，會在物理空間中變為另一個方向的移動。

- 這可以將虛擬空間中的水平運動轉換為物理空間中的垂直運動。
- 另外，如果你使用的是水平放置的機械手臂，使用此設定可以校正空間，使虛擬空間與物理空間一致。

> 值為 90 時，機器會俯仰 90 度。
> - 如果你的機械手臂是垂直放置的，那麼在虛擬空間中朝向你的運動，在物理空間中會變為向下的運動（空間中的方向不再一致）。
> - 如果你的機械手臂是水平放置的，那麼在虛擬空間中朝向你的運動，在物理空間中也會是朝向你的運動（空間中的方向一致）。
> 
> ![hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png)
> ![hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png)
> ![hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png)

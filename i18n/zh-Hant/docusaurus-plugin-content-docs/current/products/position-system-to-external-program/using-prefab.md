---
sidebar_position: 45
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 使用預製物件

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

在你[正確完成一次校準](first-time-calibration)並[連接好機械手臂](connect)之後，以下是使用預製物件的方法。

- 選單中的 **Enabled** 開關用於啟用系統。
- 選單中的 **Enabled and Visible** 開關用於啟用系統，並讓其他使用者也能看到紅色校準箭頭。
- 按住選單中的 **Bring to Hand** 按鈕，可以變更機械手臂的最低中心點。
  - 放開選單按鈕後，請讓手部保持靜止一秒鐘，以便世界位置能正確同步給其他使用者。
  - 如果你不在 *Enabled and Visible* 模式下，紅色校準箭頭將只有你自己看得到。

## VRChat {/* #vrchat */}

在 <HaiTag requiresVRChat={true} short={true} /> 中，請使用 **Expressions Menu**。

## ChilloutVR {/* #chilloutvr */}

在 <HaiTag requiresChilloutVR={true} short={true} /> 中，請使用主要大選單中的 **Adv Avtr** 按鈕。

![cvr-adv.png](@site/docs/products/position-system-to-external-program/img/cvr-adv.png)

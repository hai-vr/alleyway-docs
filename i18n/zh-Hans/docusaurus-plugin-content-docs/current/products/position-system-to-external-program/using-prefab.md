---
sidebar_position: 45
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 使用预制件

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

在你[正确完成一次校准](first-time-calibration)并[连接好机械臂](connect)之后，以下是使用预制件的方法。

- 菜单中的 **Enabled** 开关用于启用系统。
- 菜单中的 **Enabled and Visible** 开关用于启用系统，并让其他用户也能看到红色校准箭头。
- 按住菜单中的 **Bring to Hand** 按钮，可以更改机械臂的最低中心点。
  - 松开菜单按钮后，请保持手部静止一秒钟，以便世界位置能正确同步给其他用户。
  - 如果你不在 *Enabled and Visible* 模式下，红色校准箭头将只有你自己能看到。

## VRChat {/* #vrchat */}

在 <HaiTag requiresVRChat={true} short={true} /> 中，请使用 **Expressions Menu**。

## ChilloutVR {/* #chilloutvr */}

在 <HaiTag requiresChilloutVR={true} short={true} /> 中，请使用主大菜单中的 **Adv Avtr** 按钮。

![cvr-adv.png](@site/docs/products/position-system-to-external-program/img/cvr-adv.png)

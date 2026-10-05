---
sidebar_position: 45
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# プレハブを使う

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

一度[正しくキャリブレーション](first-time-calibration)して[ロボットアームを接続](connect)したら、プレハブは次のように使います。

- メニューの **Enabled** トグルでシステムを有効にします。
- メニューの **Enabled and Visible** トグルでシステムを有効にし、赤いキャリブレーション用の矢印を他のユーザーにも見えるようにします。
- メニューの **Bring to Hand** ボタンを押し続けると、ロボットアームの最下部中心点を変更できます。
  - メニューのボタンを離したら、ワールド位置が他のユーザーに正しく同期されるよう、1秒ほど手を動かさないでください。
  - *Enabled and Visible* モードでない場合、赤いキャリブレーション用の矢印は自分にしか見えません。

## VRChat {/* #vrchat */}

<HaiTag requiresVRChat={true} short={true} /> では、**Expressions Menu** を使用します。

## ChilloutVR {/* #chilloutvr */}

<HaiTag requiresChilloutVR={true} short={true} /> では、メインの大きなメニューにある **Adv Avtr** ボタンを使用します。

![cvr-adv.png](@site/docs/products/position-system-to-external-program/img/cvr-adv.png)

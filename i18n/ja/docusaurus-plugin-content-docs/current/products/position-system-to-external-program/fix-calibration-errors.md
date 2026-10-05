---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# キャリブレーションエラーの修正

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Checksum is Failing* というエラーが赤く表示される場合は、以下の考えられる問題を確認してください：

:::tip
参考として、正しく動作しているときは**下の動画**のように表示されます：

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
:::

### ピクセルがまったく表示されない {/* #the-pixels-are-completely-missing */}

<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- メニューで Enable をクリックしたことを確認してください。
- メニューで Bring to Hand をクリックしたことを確認してください。

### オーバーレイがピクセルを遮っている {/* #an-overlay-is-obstructing-the-pixels */}

<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 左目と重ならないように、オーバーレイをもっと右に移動してください。
- 左目の視野の左側に手首のオーバーレイを表示しないようにしてください。

### 領域がずれている {/* #the-area-is-shifted */}

<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- *Reset to Defaults* を押してください。それでも直らない場合は、Anchor と Offset の値を調整してください。

### 微妙な問題があり、原因がはっきりしない {/* #there-is-a-subtle-issue-and-the-cause-is-unclear */}
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- + と - のボタンを押して、ピクセルの位置をずらしてみてください。
- 別のワールドに移動してみてください。特に、現在のワールドに強いポストプロセスエフェクトがかかっている場合は有効です。
- *Reset to defaults* ボタンを押してみてください。

---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 修正校準錯誤

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

如果以紅色顯示 *檢查碼驗證失敗* 錯誤，請檢查以下可能的問題：

:::tip
作為參考，正常運作時你應該看到的是**下面這部影片**中的畫面：

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
:::

### 像素完全沒有顯示 {/* #the-pixels-are-completely-missing */}

<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 檢查你是否在選單中點擊了 Enable。
- 檢查你是否在選單中點擊了 Bring to Hand。

### 有覆蓋層擋住了像素 {/* #an-overlay-is-obstructing-the-pixels */}

<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 將覆蓋層往右移動一些，避免它與你的左眼視野重疊。
- 避免在左眼視野的左側顯示手腕覆蓋層。

### 區域發生了偏移 {/* #the-area-is-shifted */}

<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 按下 *重設為預設值*，如果仍未解決，請調整錨點和偏移的值。

### 存在細微問題，且原因不明 {/* #there-is-a-subtle-issue-and-the-cause-is-unclear */}
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 嘗試按 + 和 - 按鈕來移動像素。
- 嘗試切換到其他世界，尤其是當你目前所在的世界有強烈的後製處理效果時。
- 嘗試按下 *重設為預設值* 按鈕。

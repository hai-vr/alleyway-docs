---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 首次校準

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

首次啟動程式時，你需要進行設定以確認其能正常運作。

## 啟動程式 {/* #start-the-program */}

如果你尚未安裝，請下載 .NET 7.0 Runtime 的「Run console apps」 https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

接著，啟動 `position-system.exe`。

:::note
如果你想使用 WebSocket，請查看[開發者文件頁面](./developer#websockets)
:::

## VR 校準 {/* #vr-calibration */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} /><HaiTag requiresSteamVR={true} />
</HaiTags>

:::warning
這需要 SteamVR。如果你不使用 SteamVR，則需要使用視窗校準。

*如果你是 OpenXR 開發者，[或許可以提供協助](https://github.com/hai-vr/position-system-to-external-program/issues/1)。我還沒有時間研究這個問題。*
:::

在實際操作之前，你應該先完整閱讀以下說明。

以下校準操作需要查看一個視窗來確認是否正常運作。但是，視窗的內容取決於你在 VR 中看到的畫面。
**開啟 SteamVR 桌面視窗會遮住整個螢幕**並導致投影問題。你不能用 SteamVR 桌面視窗來確認是否正常運作。

對於首次校準，我建議將頭戴式顯示器抬起，讓它暫時架在額頭上，然後查看實際螢幕上的視窗。
下次就不需要再這樣做了。

- 在軟體中，切換到 *資料校準* 分頁。
- 如果你還沒有進入 VR，請以 VR 模式啟動你選擇的遊戲，並載入你已設定好的虛擬化身或物品。
- 你應該處於 VR 中，因為我們需要確保頭戴式顯示器的紋理已被校準。
- 開啟遊戲內選單，然後：
  - 將 **Enable** 切換為開啟。
  - 按住 **Bring to Hand** 按鈕，一秒後放開。
- 如果一切順利，你應該會在 *資料校準* 分頁上看到一條像素帶。

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

如果顯示的不是這樣，或者以紅色顯示 **檢查碼驗證失敗** 訊息，那麼：
- 確保你的 SteamVR 選單沒有開啟。
- 點擊 + 和 - 按鈕來移動像素。
- 查看[下一頁以進行進一步的疑難排解](./fix-calibration-errors)。

## 替代方案：視窗校準 {/* #alternative-window-calibration */}

:::warning
視窗校準可以使用，但不建議，因為遊戲很可能需要額外算繪一個攝影機；
此外，在某些情況下，使用攝影機可能會被視為侵犯隱私。
:::

除了使用 SteamVR，你也可以使用視窗校準。
- **如果 SteamVR 對你有效，請不要這樣做。**
- 在 *資料校準* 中，將 *提取器偏好設定* 變更為 *PrioritizeWindow*。
- 在 *視窗名稱* 欄位中，輸入視窗名稱的開頭部分。
  - 錯誤：如果我們的程式未能偵測到正確的視窗，你可能需要重新啟動應用程式。這將在之後的版本中修正。
- *如果你使用 VRChat 並處於 VR 中，請將攝影機切換為 Stream 攝影機。*

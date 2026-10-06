---
title: "Position System to External Program"
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Position System to External Program* 是一個**預製物件**和一個**程式**，可讓你將標準類 DPS 燈光的位置連接到機械手臂。

其他使用者可以透過虛擬空間遠端控制你的機械手臂的位置和旋轉。

:::tip
只有**連接**機械手臂的**電腦**需要安裝軟體和預製物件。虛擬空間中的其他使用者不需要，
他們只需要一個標準的類 DPS 燈光。

如果他們已經有標準的類 DPS 燈光（例如 SPS），就能直接控制你的機械手臂，不需要進行任何額外設定。
:::

<HaiVideo src="./img/position-system-f-noaudio.mp4"></HaiVideo>

*本軟體在 GitHub 上以 MIT 授權免費開源，因此你可以對其進行審查。*

## 運作原理 {/* #how-is-it-done */}

其原理是使用一種特殊的著色器，將像素編碼到視窗畫面或投射到頭戴式顯示器中的影像上。
接著由我們的程式讀取這些像素。

資料擷取使用的是**無害的螢幕擷取**技術，類似於視窗和 VR 直播擷取程式所使用的技術。
不會竄改任何電腦程式，也不會干預任何處理程序。也不使用 OSC。

此外：
- 也會擷取攝影機在世界空間中的位置和旋轉。這可用於將 SteamVR 覆蓋層固定在世界空間中。
- 還可以選擇開放一個 WebSocket 服務，以便從 Resonite 等虛擬空間系統控制機械手臂。

<HaiVideo src="./img/ILX73J2vHu-f.mp4"></HaiVideo>
*這種資料擷取方式與螢幕擷取類似，完全無害。*

## 相容的機械手臂 {/* #compatible-arms */}

目前，已知本軟體可與以下機械手臂搭配使用：

| 廠商          | 型號    | 協定       | 通訊方式 | 備註                                                                                  |
|-------------|-------|----------|------|:------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 序列埠  |                                                                                     |
| Tempest MAx | SR6   | T-code   | 序列埠  | ⚠️ 請務必閱讀：<br/>[修補 SR6 韌體](./firmware-patches#patching-the-sr6-firmware-file) |

:::info
如果你的裝置不在上表中，請[查看常見問題](./other)。

由於目前沒有擁有此類裝置的開發貢獻者，因此尚未支援無線連線。不過，
至少有一位 OSR2+ 使用者使用自訂韌體成功實現了 *Serial over Bluetooth*，所以無線連線是完全可行的。

如果你是開發者，[或許可以提供協助](other#my-robotic-arm-is-not-in-that-list-how-to-add-it)。
:::

<HaiVideo src="./img/resonite-position-system-f.mp4"></HaiVideo>
*在 Resonite 中，資料是透過 WebSocket 傳輸，而不是透過影像資料擷取。*

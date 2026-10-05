---
sidebar_position: 200
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 修補 SR6 韌體

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

## 修補 SR6 韌體檔案 {/* #patching-the-sr6-firmware-file */}

如果你使用 SR6，可能需要修補韌體以防止某個錯誤發生。

:::info
以下內容僅適用於使用 SR6 機械手臂的情況。
:::

### 修補 {/* #patch */}

在 `SR6-Alpha5_ESP32.ino` 的第 429 行，`SetPitchServo` 函式中，將以下這行：

```c
  float beta = acos((csq + 5625 - bsq)/(150*c)); // Angle between c-line and servo arm
```

替換為：

```c
  float beta = acos(constrain((csq + 5625 - bsq)/(150*c), -1, 1)); // Angle between c-line and servo arm
```

接著，依照 SR6 的使用說明書將韌體上傳到你的裝置。

### 原因 {/* #reason */}

在開發本軟體的過程中，我們發現該韌體存在一個錯誤，會導致向伺服馬達傳送無效的數值。

當機械手臂被指示移動到一個不尋常的位置時，就會發生這個錯誤，而在虛擬空間中，這樣的位置是實際上可能達到的。

這個錯誤的指令會使伺服馬達做出錯誤的反應，移動到一個極端位置。

因此，如果你使用 SR6，我建議你修補韌體。

<HaiVideo src="./img/firmware-f.mp4" autoWidth={false} halfWidth={true}></HaiVideo>

:::note
技術原因：一個大於 1 的值（例如 1.153）被傳入了 `acos` 函式。這會回傳 NaN。

這可能表示韌體中的逆向運動學求解器存在錯誤。
:::

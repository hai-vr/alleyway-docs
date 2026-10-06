---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 安裝

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
只有**連接**機械手臂的**電腦**需要安裝軟體和預製物件。虛擬空間中的其他使用者不需要，
他們只需要一個標準的類 DPS 燈光。

如果他們已經有標準的類 DPS 燈光（例如 SPS），就能直接控制你的機械手臂，不需要進行任何額外設定。
:::

## 下載軟體 {/* #download-software */}

可以在以下位置下載軟體：

- 下載 **[1.2.0 軟體 (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/position-system-1.2.0-executable.zip)**

如果你尚未安裝，請下載 .NET 7.0 Runtime 的「Run console apps」 https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

*如果你是開發者，可以[在 GitHub 上審查軟體原始碼](https://github.com/hai-vr/position-system-to-external-program/)。*

## 下載預製物件 {/* #download-prefab */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

下載預製物件的方法：
- 將 **Alleyway [ALCOM 儲存庫](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** 新增到你的儲存庫中。
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- 將 *Alleyway - Position System to External Program* 套件新增到你的專案中。

或者，你也可以在這裡取得 .unitypackage 檔案：

- 下載 **[1.2.0 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/dev.hai-vr.alleyway.position-system-1.2.0.unitypackage)**

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

目前還沒有可供下載的 .resonitepackage。請閱讀[虛擬化身設定文件，了解一種可行的 ProtoFlux 設定方式](./platform-setup#resonite)。

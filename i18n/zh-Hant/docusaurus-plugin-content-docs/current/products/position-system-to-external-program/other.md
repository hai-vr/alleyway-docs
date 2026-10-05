---
sidebar_position: 80
---
import HaiLocalization from "/src/components/HaiLocalization";

# 常見問題

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

### 程式的設定檔儲存在哪裡？ {/* #where-are-the-program-config-files-saved */}

設定檔儲存在 `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` 資料夾中。

### 目前哪些機械手臂裝置可以使用？ {/* #what-robotic-arm-devices-are-currently-working */}

目前，已知本軟體可與以下機械手臂搭配使用：

| 廠商          | 型號    | 協定       | 通訊方式 | 備註                                                                                  |
|-------------|-------|----------|------|:------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 序列埠  |                                                                                     |
| Tempest MAx | SR6   | T-code   | 序列埠  | ⚠️ 請務必閱讀：<br/>[修補 SR6 韌體](./firmware-patches#patching-the-sr6-firmware-file) |

由於目前沒有擁有此類裝置的開發貢獻者，因此尚未支援無線連線。不過，
至少有一位 OSR2+ 使用者使用自訂韌體成功實現了 *Serial over Bluetooth*，所以無線連線是完全可行的。

其他支援 T-code 協定的機械手臂也可能受到支援。

### 我的機械手臂不在清單中。要如何新增支援？ {/* #my-robotic-arm-is-not-in-that-list-how-to-add-it */}

如果你的裝置是由 Tempest 設計的，由於他們的裝置使用 T-code 協定，它很可能已經可以使用。
我沒有測試過這一點。

否則，你需要其他開發者的協助才能做到這一點。
我自己無法為其他裝置新增支援，因為我不太可能擁有其他類似的機械手臂。

如果你認識願意嘗試新增支援的開發者，[請讓他們查看 GitHub](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` 中的 [**Submit()** 函式](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)可能是一個不錯的切入點。

如果你的裝置只有一個運動軸，將來或許可以新增與 *Intiface* 的整合。

### 無線：機械手臂出現卡頓，或運動不順暢 {/* #wireless-the-robotic-arm-is-stuttering-or-it-is-not-smooth */}

至少有一位使用者回報過機械手臂異常卡頓的情況，而該使用者使用的是
無線通訊（透過藍牙進行的序列通訊）。結果發現，問題很可能是由電腦造成的
某種無線干擾。

如果你使用的是無線裝置，請嘗試將藍牙接收器接到 USB 延長線上，
使其遠離電腦。

### 無線速率限制 {/* #wireless-rate-limiting */}

如果你正在開發無線模組，或者正在使用透過藍牙進行序列通訊的特殊韌體，
你可能需要、也可能不需要減少每秒傳送到裝置的更新次數。

介面中的 Wireless 分頁可讓你變更更新速率。預設的更新速率為每秒 100 次。

對於無線裝置，較低的值（例如每秒 20 次更新）可能更為合理。

### 軟體的舊版本 {/* #older-versions-of-the-software */}

[安裝](./install)頁面只提供軟體和預製物件最新版本的連結。

如需舊版本，請查看 [GitHub 發行頁面](https://github.com/hai-vr/position-system-to-external-program/releases)。

所有發行版本和執行檔都是由 GitHub 的自動化基礎設施直接使用儲存庫的原始碼編譯而成。

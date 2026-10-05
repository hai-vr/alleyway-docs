---
title: 更新紀錄
sidebar_position: 100
---
import HaiLocalization from "/src/components/HaiLocalization";

# Position System to External Program - 更新紀錄

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

---

## 1.2.0

- 🌃 *預製物件和著色器沒有變更。*
- 🖥️ *程式已更新。*

新增模擬扭轉：
- 由於類 DPS 資料只包含位置和方向資訊，缺少這部分資訊，我們無法實現真正的「扭轉」。
- 新增了根據橫向位置和翻滾得出的模擬扭轉。
- 在機器人學設定中，新增了 Twist 區段來設定此模擬扭轉。

嘗試修正裝置使用藍牙序列通訊時發生的問題：
- 新增一個限制每秒更新次數的新設定，位於介面中新的 *Wireless* 分頁。

*與 1.2.0-alpha.2 相比：僅在勾選核取方塊時才顯示速率限制滑桿。*

## 1.2.0-alpha.2

- 🌃 *預製物件和著色器沒有變更。*
- 🖥️ *程式已更新。*

嘗試修正裝置使用藍牙序列通訊時發生的問題：
- 新增一個限制每秒更新次數的新設定，位於介面中新的 *Wireless* 分頁。

## 1.2.0-alpha.1

- 🌃 *預製物件和著色器沒有變更。*
- 🖥️ *程式已更新。*

新增模擬扭轉：
- 由於類 DPS 資料只包含位置和方向資訊，缺少這部分資訊，我們無法實現真正的「扭轉」。
- 新增了根據橫向位置和翻滾得出的模擬扭轉。
- 在機器人學設定中，新增了 Twist 區段來設定此模擬扭轉。

## 1.1.0

- 🌃 *預製物件和著色器沒有變更。*
- 🖥️ *程式已更新。*

新增最小高度硬限位：
- 這可防止機械手臂低於特定高度，從而限制其運動範圍。
- 勾選 *補償虛擬比例* 時，虛擬比例會在內部獲得補償，**並且**會套用一個偏移，
  使得在硬限位之間的範圍內移動時，仍然需要在虛擬空間中走完全部行程。

## 1.0.2

- 🌃 *預製物件和著色器沒有變更。*
- 🌃 *程式沒有變更。*

此版本中沒有會影響到你的變更。

`package.json` 已更新為新的說明，該說明將顯示在清單彙整器中。

## 1.0.1

- 🌃 *預製物件和著色器沒有變更。*
- 🖥️ *程式已更新。*

修正：在帶有使整個畫面變暗之後製處理的世界中，資料解碼不再失敗。
- 修正：在「for Two」世界中，總和檢查碼不再失敗。

---

## 1.0.0

正式發行。

*原始碼與 1.0.0-beta.1 完全相同，只是使用新的版本號重新建置。*

---

## 1.0.0-beta.1

- 🌃 *VRChat 預製物件和著色器沒有變更。*
- 🌕 *ChilloutVR 預製物件已變更。應使用最新版本重新上傳虛擬化身，以便使用部分功能。*

在編譯後的程式檔案中包含授權條款，並在軟體中新增了 README.txt 檔案。

為公開發行準備軟體。

其他：
- 將預設的 VR 座標從 (0, 0) 變更為 (1, 1)。

修正：
- 從 ChilloutVR 預製物件中移除了 Animator 元件。
- 修正：ChilloutVR 約束因在 Unity 2022 中儲存而無法在 Unity 2021 中運作的問題。
- 修正：旋轉機器無法立即更新的問題。
- 讓預覽模型不那麼令人困惑。

---

## 0.2.0-beta.1

💥 *重大變更：安裝此新套件之前，需要先移除舊套件。資源 GUID 不變。部分預製物件名稱有變更。*

🌕 *預製物件已變更。應使用最新版本重新上傳虛擬化身，以便使用部分功能。*

**此版本包含重大變更。**

套件名稱已縮短為 `dev.hai-vr.alleyway.position-system`。這表示在安裝此套件之前，你必須先解除安裝舊套件。

資源 GUID 不變，但部分預製物件名稱已變更。

由於本產品尚未正式宣布發行，因此主版本號不變。

### 新增 ChilloutVR 預製物件基礎 {/* #add-chilloutvr-prefab-base */}

ChilloutVR 的安裝步驟[記錄在此處](./platform-setup#chilloutvr)。

### 其他 {/* #other */}

重大變更：
- 重大變更：套件名稱已縮短為 dev.hai-vr.alleyway.position-system。
- 重大變更：重新命名預製物件以縮短其名稱。
- 重大變更：在預製物件中，縮短了網格編碼器的名稱。
- 重大變更：將 ChilloutVR 和 VRChat 的資源分到不同的資料夾中。
- 重大變更：重新命名了許多資源並將其移動到不同的資料夾中。
- 由於物件名稱有所變更：
  - 重新產生了 ChilloutVR 絕對路徑動畫。
  - 重新產生了 VRChat 相對路徑動畫。

其他：
- 新增了一個預覽網格，協助使用者依照虛擬化身身高來縮放系統。
- 將選單放入一個子選單中。
- 選單現在附有圖示。
- GitHub Releases 現在會包含一個 .unitypackage 檔案。

---

## 0.1.0-beta.7

🌃 *Unity 預製物件和著色器沒有變更。*

### 新增 ChilloutVR 預製物件基礎 {/* #add-chilloutvr-prefab-base-1 */}

ChilloutVR 的安裝步驟[記錄在此處](./platform-setup#chilloutvr)。

### 其他 {/* #other-1 */}

- GitHub Releases 現在會包含一個 .unitypackage 檔案。

---

## 0.1.0-beta.6

🌕 *Unity 著色器已變更。應使用最新版本重新上傳虛擬化身，以便使用部分功能。*

### 新功能：新增最大高度硬限位選項。 {/* #new-feature-add-a-maximum-height-hard-limit-option */}

硬限位會降低機械手臂被允許移動的最大高度。

變更此值時，虛擬比例會在內部進行補償，使得在硬限位之間的範圍內移動時，仍然需要在虛擬空間中走完全部行程。
可以透過補償虛擬比例核取方塊停用此功能。

### 新功能：新增偏移俯仰選項。 {/* #new-feature-add-an-offset-pitch-option */}

偏移可讓你在套用位置後調整機械手臂的俯仰角。

這不會改變移動的方向。虛擬空間中的移動在物理空間中仍會是相同的方向。

### 新功能：新增整體旋轉機械手臂的設定。 {/* #new-feature-add-a-setting-to-rotate-the-robotic-arm-entirely */}

使用旋轉機器設定時，虛擬空間中朝某一方向的移動，會在物理空間中變為另一個方向的移動。

- 這可以將虛擬空間中的水平運動轉換為物理空間中的垂直運動。
- 另外，如果你使用的是水平放置的機械手臂，使用此設定可以校正空間，使虛擬空間與物理空間一致。

### 新增 VRCFury 預製物件 {/* #add-vrcfury-prefab */}

VRCFury 的安裝步驟[記錄在此處](./platform-setup#vrchat-avatars-sdk-using-vrcfury)。

### 其他 {/* #other-2 */}

修正：
- 現在會忽略不可見的視窗，因此搜尋視窗名稱應該會更快。
- 編碼器網格上不再帶有已刪除的 Animation 元件（網格資源骨架的「Animation Type」現在設為 None）。

其他：
- **根 PID 控制器不穩定，因此在此版本中已停用。**
- 校準器 Gizmo 模型的材質已從 lilToon 切換為 Standard，以避免安裝預製物件時需要 lilToon。
- 由於不再需要過度考慮光暈效果，改回使用灰色像素而不是紅色像素。著色器版本已變更為 V1.0.1 以反映這一點。
- 由於 WebSocket 不僅可用於 Resonite，所有提及 Resonite WebSockets 的地方都已改為 WebSockets。
- 在除錯分頁中，提供虛擬與物理之間縮放差異的估計值。這是為將來的工作做準備，以便在攝影機因在虛擬空間中移動而開始移動時，
  在遊玩空間中重新定位物件。

---

## 0.1.0-beta.5

🌃 *Unity 預製物件和著色器沒有變更。*

修正：現在不需要在電腦上安裝 ASP.NET Core 執行階段也能啟動應用程式。
- 在不使用 AspNetCore 的情況下重新實作了 WebSocket 服務。

---

## 0.1.0-beta.4

🌕 *Unity 著色器已變更。應使用最新版本重新上傳虛擬化身，以便使用部分功能。*

### 新功能：將世界空間中的攝影機位置和旋轉新增到資料中。 {/* #new-feature-add-world-space-camera-position-and-rotation-to-the-data */}

世界空間中的攝影機位置和旋轉現在會被編碼到資料中。
此項新增的目的是提供另一種將 SteamVR 覆蓋層固定在世界空間中的方式。

著色器版本已更新為 V1.1.0。

修正：
- 修正：WebSocket 的法線現在會被正規化。

---

## 0.1.0-beta.3

🌃 *Unity 預製物件和著色器沒有變更。*

### 新功能：新增選用的 WebSocket 服務以支援 Resonite。 {/* #new-feature-add-optional-websocket-service-for-resonite-support */}

現在可以從 *Resonite* 向 WebSocket 傳送位置和法線來控制機械手臂。
由於所傳送的位置實際上模擬的是同樣的類 DPS 燈光，因此機械手臂的運動仍受機器人學分頁中設定的約束。

如果收到任何有效訊息，它將覆蓋所有資料擷取邏輯；不會再進行任何影像或資料處理。

更多詳細資訊，請參閱 [README.md 中的 *Websockets as an alternative input system* 章節](https://github.com/hai-vr/position-system-to-external-program?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

---

## 0.1.0-beta.2

🌃 *Unity 預製物件和著色器沒有變更。*

### 新功能：新增 PID 控制器以穩定機械手臂。 {/* #new-feature-add-pid-controllers-to-stabilize-the-robotic-arm */}

機器人學分頁現在提供一個自動調整根位置的 PID 控制器選項，
以及另一個用於對目標位置進行阻尼的 PID 控制器。

### 新功能：新增限制橫向軸的安全設定。 {/* #new-feature-add-safety-setting-to-clamp-the-lateral-axes */}

機器人學分頁現在提供一個將橫向移動限制在圓內的安全模式。
圓在最底部時比在最頂部時更小。

### 新功能：新增自訂虛擬縮放設定。 {/* #new-feature-add-custom-virtual-scale-setting */}

機器人學分頁現在提供用於變更虛擬世界比例的滑桿。
值越大，表示需要在虛擬空間中移動更多，才能在物理空間中產生同樣的移動量。

### 其他 {/* #other-3 */}

修正：
- 修正：任一座標為負數時 OpenVR 擷取器當機的問題。
- 預設情況下，在視窗和 VR 都未開啟時，介面不再顯示「資料正常」。

其他：
- 如果目標與根之間的距離大於 3，則忽略輸入資料。
- 從應用程式資料夾名稱中移除了波浪號。
- 將 zip 檔名變更為 position-system。

---

## 0.1.0-beta.1

### 新功能：將標準類 DPS 燈光的位置連接到機械手臂。 {/* #new-feature-connect-the-position-of-standard-dps-like-lights-to-a-robotic-arm */}

這是首個測試版。

此測試版包含一個執行檔（`.exe`），它可以：
- 解碼透過 OpenVR 紋理傳輸的類 DPS 資料。
- 解碼透過視窗傳輸的類 DPS 資料。
- 將類 DPS 資料提交到連接著使用 Tcode 協定（SR6 和 OSR2 所使用）之機械手臂的任意序列埠。

該套件包含一個預製物件和一個著色器：
- 預製物件使用 Modular Avatar 並會建立一個選單。其同步參數總成本為 2 位元。
- 預製物件不需要任何手動設定。著色器已在預製物件中設定好。

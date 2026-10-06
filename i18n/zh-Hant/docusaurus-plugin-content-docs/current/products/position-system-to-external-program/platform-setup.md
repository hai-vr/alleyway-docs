---
sidebar_position: 30
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 設定虛擬化身

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
只有**連接**機械手臂的**電腦**需要安裝軟體和預製物件。虛擬空間中的其他使用者不需要，
他們只需要一個標準的類 DPS 燈光。

如果他們已經有標準的類 DPS 燈光（例如 SPS），就能直接控制你的機械手臂，不需要進行任何額外設定。
:::

請依照你的平台或應用程式，選擇以下其中一個章節：
- [使用 Modular Avatar 的 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-modular-avatar)
- [使用 VRCFury 的 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-vrcfury)
- [**Resonite**](#resonite)
- [**ChilloutVR**](#chilloutvr)
- [使用 **Basis** 框架建置的應用程式](#applications-built-using-the-basis-framework)

## 使用 Modular Avatar 的 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-modular-avatar */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::info
如果你有 Modular Avatar，建議使用此方法。如果你沒有 Modular Avatar，但有 VRCFury，[請參閱下方的另一個章節](#vrchat-avatars-sdk-using-vrcfury)。<br/>
**你必須至少擁有這兩者之一。**

*另外，SPS 燈光也是類 DPS 燈光。它們可以與此位置系統搭配使用。*
:::

在虛擬化身中：
- 在 *Project* 分頁中，開啟 *Packages/Alleyway - Position System/Prefabs/* 資料夾。
- 將 *PositionSystem-VRC-MA* 預製物件新增到你的虛擬化身根部。

![Unity_vBn2gPNKzq.png](@site/docs/products/position-system-to-external-program/img/Unity_vBn2gPNKzq.png)

你可以進一步自訂設定，以下步驟為選用：
- 你可以縮放 *System* 物件。黃色桿子的長度大約相當於機械手臂的總行程。
- 如果你想變更選單位置，`(prefab)/System` 中有一個 *MA Menu Installer* 元件。
- 預設情況下，校準原點位於右手。
    - 你可以使用位於 `(prefab)/System/HandRoot` 的 *Armature Link* 元件將其切換到左手。
    - 應該將其設為慣用手還是非慣用手並沒有明確答案。我個人將其設定在慣用手上。
    - 其子物件 *HandPalmDown* 會懸浮在你的手掌下方，距離手部大約兩隻手的距離。

如果你使用會合併網格的虛擬化身最佳化工具，請排除此物件：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 這個網格很特殊，不得被轉換或簡化。

## 使用 VRCFury 的 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-vrcfury */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::note
我自己的專案不使用 VRCFury，對它的元件也不夠熟悉。儘管如此，我還是參照 Modular Avatar 預製物件，
使用對等的元件嘗試製作了 VRCFury 預製物件。

但是，我無法保證 VRCFury 預製物件的設定是正確的。

*另外，SPS 燈光也是類 DPS 燈光。它們可以與此位置系統搭配使用。*
:::

在虛擬化身中：
- 在 *Project* 分頁中，開啟 *Packages/Alleyway - Position System/Prefabs/* 資料夾。
- 將 *PositionSystem-VRC-VRCFury* 預製物件新增到你的虛擬化身根部。

![5bbBMWuP85.png](@site/docs/products/position-system-to-external-program/img/5bbBMWuP85.png)

你可以進一步自訂設定，以下步驟為選用：
- 你可以縮放 *System* 物件。黃色桿子的長度大約相當於機械手臂的總行程。
- 如果你想變更選單位置，`(prefab)/System` 中有一個 *Full Controller* 元件。
- 預設情況下，校準原點位於右手。
    - 你可以使用位於 `(prefab)/System/HandRoot` 的 *Armature Link* 元件將其切換到左手。
    - 應該將其設為慣用手還是非慣用手並沒有明確答案。我個人將其設定在慣用手上。
    - 其子物件 *HandPalmDown* 會懸浮在你的手掌下方，距離手部大約兩隻手的距離。

如果你使用會合併網格的虛擬化身最佳化工具，請排除此物件：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 這個網格很特殊，不得被轉換或簡化。

## VRChat Worlds SDK {/* #vrchat-worlds-sdk */}

:::danger
🚫 **我們不建議將著色器資料編碼系統整合到世界中。**

這是因為使用者可能需要自訂著色器材質，以修正頭戴式顯示器內的對齊問題。
:::

目前不支援世界。不過，請考慮以下幾點：

類 DPS 燈光並不侷限於虛擬化身。如果你希望由世界來控制機械手臂，或許可以
使用相同的類 DPS 燈光設定。

此外，我們支援 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)；
如果你在為自己製作世界，也可以撰寫一個向 WebSocket 提交指令的日誌剖析器。

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

Resonite 支援 WebSocket，可用於擷取位置和法線。

在一個物件中建立 *WebsocketClient* 元件。使用 *Websocket Text Message Sender* 節點傳送文字訊息。
- 我們會在連接埠 **56247** 上開放一個 WebSocket，網址為 `ws://localhost:56247/ws`
- 文字訊息字串的格式需要符合 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system) 文件中的規定。
- 傳入指定座標空間中的位置（例如本地變換或全域變換）。
- 傳入與位置處於同一座標空間的方向（例如 Up 或 Forward 方向之類）。
- *你也可以選擇傳入一個切線（例如 Up 或 Forward 方向之類），它應與方向垂直。我們目前尚未使用該資訊，但將來可能會用它來控制扭轉。*

使用軟體時，[你需要啟用 WebSocket 服務，因為它預設是關閉的](developer#websockets)。

目前我們沒有提供可直接使用的 ProtoFlux 物品。請參考下圖了解一種可行的實作方式。

:::note
既然你在讀這段內容，你對 ProtoFlux 的了解可能比我更深，所以如果你發現這張藍圖中有明顯錯誤，
請不要照抄。

例如，這應該只在連接機械手臂的電腦上執行，但這張圖目前並沒有加以限制。
:::

[![resonite_websocket.jpg](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)

## ChilloutVR {/* #chilloutvr */}

<HaiTags>
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

:::danger
將 ChilloutVR 預製物件新增到虛擬化身上有些困難，你需要將你的基礎動畫控制器與我們的動畫控制器合併，
而我不知道如何俐落地完成這一步。

可能會出現問題，所以如果你要嘗試，請做好心理準備。
:::

已嘗試性地新增了一個預製物件。

- 在 *Project* 分頁中，開啟 *Packages/Alleyway - Position System/Prefabs/* 資料夾。
- 將 *PositionSystem-ChilloutVR* 預製物件新增到你的虛擬化身根部。
- 它**必須**位於虛擬化身根部。**不要重新命名**預製物件。動畫依賴於它。

![Unity_XEqPy4mBCe.png](@site/docs/products/position-system-to-external-program/img/Unity_XEqPy4mBCe.png)

如果你想解除預製物件的封裝：
- 解除預製物件的封裝。
- 將 HandRoot 和 NeckRoot 物件分別移動到你的手部骨骼和頸部骨骼。
  - 應該將 HandRoot 指派給慣用手還是非慣用手並沒有明確答案。我個人將其設定在慣用手上。
  - 其子物件 *HandPalmDown* 會懸浮在你的手掌下方，距離手部大約兩隻手的距離。
- 將它們的本地位置設為零。

:::note
如果你想在不解除預製物件封裝的情況下完成此操作，請改為執行以下步驟：
- 將 HandRoot 和 NeckRoot 物件的**複本**分別建立到你的手部骨骼和頸部骨骼上。
  - 應該將 HandRoot 指派給慣用手還是非慣用手並沒有明確答案。我個人將其設定在慣用手上。
  - 其子物件 *HandPalmDown* 會懸浮在你的手掌下方，距離手部大約兩隻手的距離。
- 將它們的本地位置設為零。
- 在預製物件中，找到 `(prefab)/System/CalibrationConstraint`。
- 在 *Position Constraint* 元件中，將約束來源重新指派為你新的 HandRoot 物件。
- 在 *Aim Constraint* 元件中，將約束來源重新指派為你新的 NeckRoot 物件。
:::

設定你的動畫控制器：
- 在 Project 檢視中，前往 `Packages/Alleyway - Position System/Internal/App-ChilloutVR/AbsolutePaths/`
- 開啟 `PositionSystem-Animator-CVR-Absolute.controller` 動畫控制器資源檔案，
- 將其中的兩個圖層複製到你自己的動畫控制器中，包括參數和參數的值 **（TODO：這要怎麼做？？？）**。

設定你的 *CVR Avatar* 元件：
- 在 Advanced Settings 中：
  - 新增一個名為 *Enabled* 的 Float 類型 Toggle，用於切換參數 `PStoEP_Enabled`
  - 新增一個名為 *Enabled and Visible* 的 Float 類型 Toggle，用於切換參數 `PStoEP_EnabledAndVisible`
  - 新增一個名為 *Bring to Hand* 的 Float 類型 Toggle，用於切換參數 `PStoEP_BringToHand`

選用：
- 你可以縮放 *System* 物件。黃色桿子的長度大約相當於機械手臂的總行程。

:::info[給 ChilloutVR 進階使用者的補充資訊]

以下內容可以幫助你了解如何轉換這個預製物件。

物件結構：
- 將 `(prefab)/System/HandRoot` 重新設為你其中一隻手的子物件，這隻手將用於校準原點。
    - 應該將其設為慣用手還是非慣用手並沒有明確答案。我個人將其設定在慣用手上。
    - 其子物件 *HandPalmDown* 會懸浮在你的手掌下方，距離手部大約兩隻手的距離。
- 將 `(prefab)/System/NeckRoot` 重新設為你頸部骨骼的子物件。

元件操作/動畫：
- 使用該著色器的編碼器網格只需對擁有連接機械手臂之電腦的人可見（虛擬化身穿戴者，
  或生成該物品的使用者）。
- 有一些約束已被轉換為 Unity 系統，並附帶相應的動畫。ChilloutVR 中的動畫邏輯有所不同，因為它使用的是世界物件預製物件技巧。

如果你可以修改 ChilloutVR，也可以考慮使用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。
:::

## 使用 Basis 框架建置的應用程式 {/* #applications-built-using-the-basis-framework */}

<HaiTags>
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

由於 Basis 專案允許修改，最簡單的方法是**不要**使用透過螢幕像素進行的資料擷取。

請改用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

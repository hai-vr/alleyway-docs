---
sidebar_position: 150
title: 開發者文件
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 開發者文件

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

本網站的大部分文件是寫給應用程式使用者的。

如果你是開發者，應查閱 [GitHub 上的 README.md](https://github.com/hai-vr/position-system-to-external-program/)，
以取得有關擷取過程、著色器、WebSocket API 以及攝影機位置擷取的技術資訊。

## 為其他機械手臂新增支援 {/* #adding-support-for-other-robotic-arms */}

你是想連接一款尚未支援的機械手臂的開發者嗎？[請查看 GitHub](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` 中的 [**Submit()** 函式](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)可能是一個不錯的切入點。

## WebSocket {/* #websockets */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

如果你在使用 *Resonite*，或者在修改 *ChilloutVR*，又或者在開發以 Basis 框架建置的應用程式，
你可能應該使用 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)。

在軟體的 *資料校準* 分頁底部的 *Resonite WebSockets* 區段，勾選核取方塊以啟用 WebSocket 服務。

![position-system_CUz03IfbdR.png](@site/docs/products/position-system-to-external-program/img/position-system_CUz03IfbdR.png)

你可以在[這裡找到 WebSocket 訊息規格](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)：

> 如果啟用了 *WebSocket* 支援，我們會在連接埠 **56247** 上開放一個 WebSocket，網址為 `ws://localhost:56247/ws`
> 
> 向其傳送以下字串，表示已解析的位置和法線：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ
> ```
> - *PositionX*、*PositionY*、*PositionZ* 是本地空間中的位置，其中 (0, 0, 0) 是最底部的中心，(0, 1, 0) 是最頂部的中心。
> - *NormalX*、*NormalY*、*NormalZ* 是方向，以長度為 1 的向量表示。即使你沒有將其長度設為 1 也沒關係，我們無論如何都會將其正規化。
> 
> 順帶一提，你也可以提交切線，它可用於定義扭轉，但這是選用的：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ TangentX TangentY TangentZ
> ```
> - *TangentX*、*TangentY*、*TangentZ* 是切線（一個與方向垂直的向量），以長度為 1 的向量表示。即使你沒有將其長度設為 1 也沒關係，我們無論如何都會將其正規化。

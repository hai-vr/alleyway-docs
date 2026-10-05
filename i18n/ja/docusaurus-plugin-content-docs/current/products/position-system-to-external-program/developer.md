---
sidebar_position: 150
title: 開発者向けドキュメント
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 開発者向けドキュメント

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

このウェブサイトのドキュメントのほとんどは、アプリケーションのユーザー向けです。

開発者の方は、抽出処理、シェーダー、WebSocket API、カメラ位置の抽出に関する技術情報について、
[GitHubのREADME.md](https://github.com/hai-vr/position-system-to-external-program/)をご覧ください。

## 他のロボットアームへの対応を追加する {/* #adding-support-for-other-robotic-arms */}

未対応のロボットアームを接続したい開発者の方は、[GitHubをご覧ください](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` にある [**Submit()** 関数](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)から始めるのがよいでしょう。

## WebSocket {/* #websockets */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

*Resonite* を使用している場合、*ChilloutVR* を改造している場合、またはBasisフレームワークでアプリケーションを構築している場合は、
[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)を使うのがよいでしょう。

ソフトウェアの *Data calibration* タブの下部にある *Resonite WebSockets* セクションで、チェックボックスをオンにしてWebSocketサービスを有効にします。

![position-system_CUz03IfbdR.png](@site/docs/products/position-system-to-external-program/img/position-system_CUz03IfbdR.png)

[WebSocketのメッセージ仕様はこちら](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)で確認できます：

> *WebSocket* サポートが有効な場合、ポート **56247** で、URL `ws://localhost:56247/ws` にWebSocketを公開します。
> 
> 解釈済みの位置と法線を表す、次の文字列を送信してください：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ
> ```
> - *PositionX*、*PositionY*、*PositionZ* はローカル空間での位置で、(0, 0, 0) が最下部の中心、(0, 1, 0) が最上部の中心です。
> - *NormalX*、*NormalY*、*NormalZ* は方向で、長さ1のベクトルで表します。長さを1にしなくても、こちらで正規化するので問題ありません。
> 
> ついでに、ひねりの定義に役立つ接線を送信することもできますが、これは任意です：
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ TangentX TangentY TangentZ
> ```
> - *TangentX*、*TangentY*、*TangentZ* は接線（方向に垂直なベクトル）で、長さ1のベクトルで表します。長さを1にしなくても、こちらで正規化するので問題ありません。

---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 初回キャリブレーション

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

プログラムを初めて起動するときは、動作することを確認するための設定が必要です。

## プログラムを起動する {/* #start-the-program */}

まだお持ちでない場合は、.NET 7.0 Runtime の「Run console apps」をダウンロードしてください https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

次に、`position-system.exe` を起動します。

:::note
WebSocketを使用したい場合は、[開発者向けドキュメントのページ](./developer#websockets)をご確認ください。
:::

## VRでのキャリブレーション {/* #vr-calibration */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} /><HaiTag requiresSteamVR={true} />
</HaiTags>

:::warning
これにはSteamVRが必要です。SteamVRを使用していない場合は、ウィンドウでのキャリブレーションを使用する必要があります。

*OpenXRの開発者の方は、[ご協力いただけるかもしれません](https://github.com/hai-vr/position-system-to-external-program/issues/1)。私はまだこれを調べる時間がありません。*
:::

実際に作業を始める前に、以下の手順を最後まで読んでください。

以下のキャリブレーション作業では、ウィンドウを見て動作を確認します。ただし、ウィンドウの内容はVRで見ているものによって変わります。
**SteamVRのデスクトップウィンドウを開くと画面全体が覆われ**、投影の問題が発生します。動作の確認にSteamVRのデスクトップウィンドウを使うことはできません。

初回のキャリブレーションでは、ヘッドセットを持ち上げて一時的に額に乗せ、実際のモニター画面のウィンドウを確認することをおすすめします。
次回以降はこれを行う必要はありません。

- ソフトウェアで *Data calibration* タブに切り替えます。
- まだVRに入っていない場合は、お好みのゲームをVRモードで起動し、設定済みのアバターまたはアイテムを読み込みます。
- HMDのテクスチャがキャリブレーションされていることを確認する必要があるため、VRに入っている必要があります。
- ゲーム内メニューを開いて：
  - **Enable** をONにします。
  - **Bring to Hand** ボタンを押し続け、1秒ほどしてから離します。
- すべてうまくいけば、*Data calibration* タブにピクセルの帯が表示されます。

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

このように表示されない場合、または **Checksum is failing** というメッセージが赤く表示される場合は：
- SteamVRメニューが開いていないことを確認してください。
- + と - のボタンをクリックして、ピクセルの位置をずらしてください。
- [さらなるトラブルシューティングについては次のページ](./fix-calibration-errors)をご確認ください。

## 代替手段：ウィンドウでのキャリブレーション {/* #alternative-window-calibration */}

:::warning
ウィンドウでのキャリブレーションも動作しますが、ゲームが別のカメラを描画する必要がある可能性が高いため、おすすめしません。
また、状況によっては、カメラの使用がプライバシーの侵害と見なされることがあります。
:::

SteamVRを使用する代わりに、ウィンドウでのキャリブレーションを使用することもできます。
- **SteamVRで問題なく動作する場合は、これを行わないでください。**
- *Data calibration* で、Extractor preference を *PrioritizeWindow* に変更します。
- *Window name* フィールドに、ウィンドウ名の先頭部分を入力します。
  - バグ：当プログラムが正しいウィンドウを検出できない場合は、アプリケーションを再起動する必要があるかもしれません。これは今後のバージョンで修正される予定です。
- *VRChatを使用していてVRに入っている場合は、カメラをStreamカメラに変更してください。*

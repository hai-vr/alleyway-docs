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

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Position System to External Program* は、標準的なDPS系ライトの位置をロボットアームに接続できる**プレハブ**と**プログラム**です。

仮想空間を通じて、他のユーザーがあなたのロボットアームの位置と回転をリモートで操作できます。

:::tip
ソフトウェアとプレハブが必要なのは、ロボットアームが**接続されているコンピューター**だけです。仮想空間にいる他のユーザーには必要なく、
標準的なDPS系ライトがあれば十分です。

SPSのような標準的なDPS系ライトをすでに持っているユーザーであれば、追加の設定なしでそのままあなたのロボットアームを操作できます。
:::

<HaiVideo src="./img/position-system-f-noaudio.mp4"></HaiVideo>

*このソフトウェアはMITライセンスのもとGitHubで公開されている無料のオープンソースソフトウェアなので、内容を監査できます。*

## 仕組み {/* #how-is-it-done */}

特殊なシェーダーを使って、ウィンドウ画面またはHMDに投影される映像にピクセルをエンコードすることで実現しています。
そのピクセルを当プログラムが読み取ります。

データの抽出には、ウィンドウやVRのライブ配信用キャプチャプログラムと同様の**無害な画面キャプチャ**技術を使用しています。
対象のプログラムを改ざんすることも、プロセスに干渉することもありません。OSCも使用していません。

さらに：
- ワールド空間におけるカメラの位置と回転も抽出されます。これはSteamVRオーバーレイをワールド空間に固定するために使用できます。
- オプションで、ResoniteのようなVR空間のシステムからロボットアームを操作できるようにWebSocketサービスを公開します。

<HaiVideo src="./img/ILX73J2vHu-f.mp4"></HaiVideo>
*データの抽出方法は画面キャプチャと同様で、まったく無害です。*

## 対応アーム {/* #compatible-arms */}

現在、このソフトウェアは以下のロボットアームで動作することが確認されています：

| ベンダー        | モデル   | プロトコル    | 通信方式     | 備考                                                                                     |
|-------------|-------|----------|----------|:---------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | シリアルポート |                                                                                        |
| Tempest MAx | SR6   | T-code   | シリアルポート | ⚠️ 必ずお読みください：<br/>[SR6ファームウェアのパッチ](./firmware-patches#patching-the-sr6-firmware-file) |

:::info
お使いのデバイスが上の表にない場合は、[FAQをご確認ください](./other)。

該当するデバイスを所有している開発協力者が現在いないため、ワイヤレスにはまだ対応していません。ただし、
カスタムファームウェアを使って *Serial over Bluetooth* での接続に成功したOSR2+ユーザーが少なくとも1人いるため、ワイヤレス対応は十分に可能です。

開発者の方は、[ご協力いただけるかもしれません](other#my-robotic-arm-is-not-in-that-list-how-to-add-it)。
:::

<HaiVideo src="./img/resonite-position-system-f.mp4"></HaiVideo>
*Resoniteでは、画像データの抽出ではなくWebSocketを使ってデータを送信します。*

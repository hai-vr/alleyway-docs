---
sidebar_position: 43
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# ロボットアームを接続する

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

- デバイスをUSBで接続します。
- ロボットアームの電源を入れます。
- *Connect to device on serial port COM...* をクリックします。
    - 複数のシリアルポートデバイスを接続している場合は、事前にドロップダウン（COM3、COM4、...）で正しいものを選択してください。
    - *USBで接続された3Dプリンターをお持ちの場合は、そのシリアルポートを選択しないよう注意してください。わからない場合は、3Dプリンターの電源を切ってください。*
- デバイスが正常に接続されると、*Connect to device* ボタンが消えます。

<HaiVideo src="./img/position-system_oXuowuZshv.mp4"></HaiVideo>

:::note
USBが正常に接続されていても、ロボットアームの電源がONになっていることを確認してください。

デバイスによっては、本体の他の部分の電源がOFFのままでも、ファンが回った状態でUSBに接続できるものがあります。
:::

## トラブルシューティング {/* #troubleshooting */}

デバイスが正常に接続されると、*Connect to device* ボタンが消えます。

ボタンが消えない場合は、以下を確認してください：
- 1つのシリアルポートに同時に接続できるプログラムは1つだけです。ロボットアームの使用やテストに他のソフトウェアを
  使っていた場合、それが当ソフトウェアの接続を妨げている可能性があります。
  - その場合は、他のプログラムを閉じてから、もう一度ボタンをクリックしてみてください。
- それでもうまくいかない場合は、デバイスのUSBケーブルを抜いて、もう一度挿し直してください。USBケーブルを
  抜くとそのデバイスへの既存の接続がすべて解除されるので、もう一度ボタンをクリックしてみてください。
- 当プログラムを二重に起動していないか確認してください。当プログラムは1つだけ起動してください。

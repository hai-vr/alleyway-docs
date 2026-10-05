---
sidebar_position: 200
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# SR6ファームウェアのパッチ

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

## SR6ファームウェアファイルのパッチ {/* #patching-the-sr6-firmware-file */}

SR6を使用している場合は、バグの発生を防ぐためにファームウェアにパッチを当てる必要があるかもしれません。

:::info
以下は、SR6ロボットアームを使用している場合にのみ該当します。
:::

### パッチ {/* #patch */}

`SR6-Alpha5_ESP32.ino` の429行目、`SetPitchServo` 関数内の次の行を：

```c
  float beta = acos((csq + 5625 - bsq)/(150*c)); // Angle between c-line and servo arm
```

次のように置き換えます：

```c
  float beta = acos(constrain((csq + 5625 - bsq)/(150*c), -1, 1)); // Angle between c-line and servo arm
```

次に、SR6の取扱説明書に従ってファームウェアをデバイスにアップロードします。

### 理由 {/* #reason */}

このソフトウェアの開発中に、ファームウェアにサーボモーターへ無効な数値を送ってしまうバグがあることがわかりました。

このバグは、ロボットアームが通常とは異なる位置への移動を指示されたときに発生します。そうした位置には、仮想空間では現実的に到達し得ます。

この誤った指示により、サーボモーターが誤って反応し、極端な位置に移動してしまいます。

そのため、SR6を使用している場合は、ファームウェアにパッチを当てることをおすすめします。

<HaiVideo src="./img/firmware-f.mp4" autoWidth={false} halfWidth={true}></HaiVideo>

:::note
技術的な理由：1.153 のような1より大きい値が `acos` 関数に渡されます。これは NaN を返します。

これはおそらく、ファームウェア内の逆運動学ソルバーに誤りがあることを示しています。
:::

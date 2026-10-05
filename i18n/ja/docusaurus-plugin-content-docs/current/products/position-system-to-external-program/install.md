---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# インストール

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
ソフトウェアとプレハブが必要なのは、ロボットアームが**接続されているコンピューター**だけです。仮想空間にいる他のユーザーには必要なく、
標準的なDPS系ライトがあれば十分です。

SPSのような標準的なDPS系ライトをすでに持っているユーザーであれば、追加の設定なしでそのままあなたのロボットアームを操作できます。
:::

## ソフトウェアのダウンロード {/* #download-software */}

ソフトウェアは以下からダウンロードできます：

- **[1.2.0 ソフトウェア (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/position-system-1.2.0-executable.zip)** をダウンロード

まだお持ちでない場合は、.NET 7.0 Runtime の「Run console apps」をダウンロードしてください https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

*開発者の方は、[GitHubでソフトウェアのソースコードを監査](https://github.com/hai-vr/position-system-to-external-program/)できます。*

## プレハブのダウンロード {/* #download-prefab */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

プレハブをダウンロードするには：
- **Alleyway の [ALCOMリポジトリ](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** をリポジトリに追加します。
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- *Alleyway - Position System to External Program* パッケージをプロジェクトに追加します。

または、こちらから .unitypackage ファイルを入手することもできます：

- **[1.2.0 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/dev.hai-vr.alleyway.position-system-1.2.0.unitypackage)** をダウンロード

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

現在、ダウンロード可能な .resonitepackage はまだありません。[ProtoFluxでの設定例についてはアバター設定のドキュメント](./platform-setup#resonite)をお読みください。

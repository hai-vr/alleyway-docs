---
sidebar_position: 30
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# アバターの設定

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
ソフトウェアとプレハブが必要なのは、ロボットアームが**接続されているコンピューター**だけです。仮想空間にいる他のユーザーには必要なく、
標準的なDPS系ライトがあれば十分です。

SPSのような標準的なDPS系ライトをすでに持っているユーザーであれば、追加の設定なしでそのままあなたのロボットアームを操作できます。
:::

お使いのプラットフォームまたはアプリケーションに応じて、以下のセクションから1つを選んでください：
- [Modular Avatarを使用する **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-modular-avatar)
- [VRCFuryを使用する **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-vrcfury)
- [**Resonite**](#resonite)
- [**ChilloutVR**](#chilloutvr)
- [**Basis** フレームワークで構築されたアプリケーション](#applications-built-using-the-basis-framework)

## Modular Avatarを使用するVRChat Avatars SDK {/* #vrchat-avatars-sdk-using-modular-avatar */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::info
Modular Avatarをお持ちの場合は、この方法をおすすめします。Modular Avatarはないが、VRCFuryはお持ちの場合は、[下の別のセクションをご覧ください](#vrchat-avatars-sdk-using-vrcfury)。<br/>
**この2つのうち、少なくとも1つが必要です。**

*また、SPSライトはDPS系ライトです。このポジションシステムで動作します。*
:::

アバターで：
- *Project* タブで、*Packages/Alleyway - Position System/Prefabs/* フォルダーを開きます。
- *PositionSystem-VRC-MA* プレハブをアバターのルートに追加します。

![Unity_vBn2gPNKzq.png](@site/docs/products/position-system-to-external-program/img/Unity_vBn2gPNKzq.png)

さらにカスタマイズすることもできます。以下の手順は任意です：
- *System* オブジェクトのスケールを変更できます。黄色い棒の長さが、ロボットアームの総移動距離のおおよその目安です。
- メニューの場所を変更したい場合は、`(prefab)/System` に *MA Menu Installer* コンポーネントがあります。
- デフォルトでは、キャリブレーションの原点は右手になります。
    - `(prefab)/System/HandRoot` にある *Armature Link* コンポーネントを使って、左手に切り替えることができます。
    - 利き手と利き手でない手のどちらに設定すべきかは、はっきりしません。私は利き手に設定しています。
    - 子オブジェクトの *HandPalmDown* は手のひらの下、手からおよそ手2つ分の距離に浮かびます。

メッシュを結合するアバター最適化ツールを使用している場合は、このオブジェクトを除外してください：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- このメッシュは特殊なものであり、変換や簡略化をしてはいけません。

## VRCFuryを使用するVRChat Avatars SDK {/* #vrchat-avatars-sdk-using-vrcfury */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::note
私は自分のプロジェクトでVRCFuryを使用しておらず、そのコンポーネントにも詳しくありません。それでも、Modular Avatarのプレハブをもとに、
同等のコンポーネントを使ってVRCFuryのプレハブを試験的に作成しました。

ただし、VRCFuryのプレハブが正しく設定されていることは保証できません。

*また、SPSライトはDPS系ライトです。このポジションシステムで動作します。*
:::

アバターで：
- *Project* タブで、*Packages/Alleyway - Position System/Prefabs/* フォルダーを開きます。
- *PositionSystem-VRC-VRCFury* プレハブをアバターのルートに追加します。

![5bbBMWuP85.png](@site/docs/products/position-system-to-external-program/img/5bbBMWuP85.png)

さらにカスタマイズすることもできます。以下の手順は任意です：
- *System* オブジェクトのスケールを変更できます。黄色い棒の長さが、ロボットアームの総移動距離のおおよその目安です。
- メニューの場所を変更したい場合は、`(prefab)/System` に *Full Controller* コンポーネントがあります。
- デフォルトでは、キャリブレーションの原点は右手になります。
    - `(prefab)/System/HandRoot` にある *Armature Link* コンポーネントを使って、左手に切り替えることができます。
    - 利き手と利き手でない手のどちらに設定すべきかは、はっきりしません。私は利き手に設定しています。
    - 子オブジェクトの *HandPalmDown* は手のひらの下、手からおよそ手2つ分の距離に浮かびます。

メッシュを結合するアバター最適化ツールを使用している場合は、このオブジェクトを除外してください：
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- このメッシュは特殊なものであり、変換や簡略化をしてはいけません。

## VRChat Worlds SDK {/* #vrchat-worlds-sdk */}

:::danger
🚫 **シェーダーによるデータエンコーダーシステムをワールドに組み込むことはおすすめしません。**

HMD内での位置ずれを修正するために、ユーザーがシェーダーのマテリアルをカスタマイズする必要がある場合があるためです。
:::

ワールドには対応していません。ただし、以下の点を検討してください：

DPS系ライトはアバターに限定されません。ワールドからロボットアームを操作したい場合は、
同じDPS系ライトの設定を使用できる可能性があります。

また、[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)にも対応しています。
自分用のワールドを作成している場合は、WebSocketにコマンドを送信するログパーサーを作成することもできます。

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

ResoniteはWebSocketに対応しており、これを使って位置と法線を取り出すことができます。

オブジェクトに *WebsocketClient* コンポーネントを作成します。*Websocket Text Message Sender* ノードを使ってテキストメッセージを送信します。
- ポート **56247** で、URL `ws://localhost:56247/ws` にWebSocketを公開します。
- テキストメッセージの文字列は、[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)のドキュメントで指定された形式にする必要があります。
- 任意の座標空間での位置（例：ローカルトランスフォームやグローバルトランスフォーム）を渡します。
- 位置と同じ座標空間での方向（例：UpやForwardの方向など）を渡します。
- *任意で、方向に垂直な接線（例：UpやForwardの方向など）も渡すことができます。この情報はまだ使用していませんが、将来的にひねりの制御に使用される可能性があります。*

ソフトウェアを使用する際は、[WebSocketサービスはデフォルトでOFFになっているため、有効にする必要があります](developer#websockets)。

現時点では、すぐに使えるProtoFluxアイテムは提供していません。実装例の参考として、下の画像を使用してください。

:::note
これを読んでいるあなたは、おそらく私よりもProtoFluxに詳しいでしょう。この設計図に明らかな間違いがあれば、
そのままコピーしないでください。

たとえば、これはロボットアームが接続されているコンピューターでのみ実行されるべきですが、このグラフでは現在その制限をしていません。
:::

[![resonite_websocket.jpg](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)

## ChilloutVR {/* #chilloutvr */}

<HaiTags>
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

:::danger
ChilloutVRのプレハブをアバターに追加するのは少し難しく、ベースのアニメーターと当方のアニメーターを結合する必要があります。
私はこの手順をきれいに行う方法を知りません。

問題が起こる可能性があるので、試す場合は覚悟して臨んでください。
:::

プレハブを試験的に追加しました。

- *Project* タブで、*Packages/Alleyway - Position System/Prefabs/* フォルダーを開きます。
- *PositionSystem-ChilloutVR* プレハブをアバターのルートに追加します。
- アバターのルートに置く**必要があります**。プレハブのオブジェクトの**名前を変更しないでください**。アニメーションがその名前に依存しています。

![Unity_XEqPy4mBCe.png](@site/docs/products/position-system-to-external-program/img/Unity_XEqPy4mBCe.png)

プレハブを展開したい場合：
- プレハブを展開します。
- HandRootオブジェクトとNeckRootオブジェクトを、それぞれ手のボーンと首のボーンに移動します。
  - HandRootを利き手と利き手でない手のどちらに割り当てるべきかは、はっきりしません。私は利き手に設定しています。
  - 子オブジェクトの *HandPalmDown* は手のひらの下、手からおよそ手2つ分の距離に浮かびます。
- それらのローカル位置をゼロに設定します。

:::note
プレハブを展開せずにこれを行いたい場合は、代わりに以下を行ってください：
- HandRootオブジェクトとNeckRootオブジェクトの**複製を作成し**、それぞれ手のボーンと首のボーンに配置します。
  - HandRootを利き手と利き手でない手のどちらに割り当てるべきかは、はっきりしません。私は利き手に設定しています。
  - 子オブジェクトの *HandPalmDown* は手のひらの下、手からおよそ手2つ分の距離に浮かびます。
- それらのローカル位置をゼロに設定します。
- プレハブ内で `(prefab)/System/CalibrationConstraint` を見つけます。
- *Position Constraint* コンポーネントで、コンストレイントのソースを新しいHandRootオブジェクトに割り当て直します。
- *Aim Constraint* コンポーネントで、コンストレイントのソースを新しいNeckRootオブジェクトに割り当て直します。
:::

アニメーターを設定します：
- Projectビューで `Packages/Alleyway - Position System/Internal/App-ChilloutVR/AbsolutePaths/` に移動します。
- `PositionSystem-Animator-CVR-Absolute.controller` アニメーターコントローラーのアセットファイルを開きます。
- 2つのレイヤーを、パラメーターとパラメーターの値も含めて、自分のアニメーターにコピーします **（TODO：これはどうやるのでしょう？？？）**。

*CVR Avatar* コンポーネントを設定します：
- Advanced Settings で：
  - パラメーター `PStoEP_Enabled` を切り替える、*Enabled* という名前のFloat型のToggleを追加します。
  - パラメーター `PStoEP_EnabledAndVisible` を切り替える、*Enabled and Visible* という名前のFloat型のToggleを追加します。
  - パラメーター `PStoEP_BringToHand` を切り替える、*Bring to Hand* という名前のFloat型のToggleを追加します。

任意で：
- *System* オブジェクトのスケールを変更できます。黄色い棒の長さが、ロボットアームの総移動距離のおおよその目安です。

:::info[ChilloutVRの上級ユーザー向けの追加情報]

以下は、このプレハブを変換する方法についての手がかりです。

オブジェクト構造：
- `(prefab)/System/HandRoot` を、原点のキャリブレーションに使用するどちらかの手の子にします。
    - 利き手と利き手でない手のどちらに設定すべきかは、はっきりしません。私は利き手に設定しています。
    - 子オブジェクトの *HandPalmDown* は手のひらの下、手からおよそ手2つ分の距離に浮かびます。
- `(prefab)/System/NeckRoot` を首のボーンの子にします。

コンポーネントの操作／アニメーション：
- シェーダーを使用するエンコーダーメッシュは、ロボットアームが接続されたコンピューターを持つ人（アバターの着用者、
  またはアイテムをスポーンしたユーザー）にのみ見える必要があります。
- Unityのシステムに変換されたコンストレイントがあり、それに伴うアニメーションもあります。ChilloutVRではワールドオブジェクトプレハブのトリックを使用しているため、アニメーションのロジックが異なります。

ChilloutVRを改造できる場合は、[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)の使用を検討することもできます。
:::

## Basisフレームワークで構築されたアプリケーション {/* #applications-built-using-the-basis-framework */}

<HaiTags>
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

Basisのプロジェクトは改造が可能なので、画面上のピクセルを通じたデータ抽出を**使わない**のが最も簡単な方法です。

代わりに[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)を使用してください。

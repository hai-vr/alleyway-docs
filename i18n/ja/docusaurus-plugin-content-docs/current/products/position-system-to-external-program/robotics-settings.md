---
sidebar_position: 50
---
import HaiLocalization from "/src/components/HaiLocalization";

# Robotics の設定

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

Robotics タブの設定では、使用中のロボットアームの動作をカスタマイズできます。

行う内容によっては、これらの設定をその場で調整する必要があるかもしれません。

## Virtual scale {/* #virtual-scale */}

*Virtual scale* は、物理空間で同じ量の動きを生み出すために仮想空間で必要な動きの量を変更します。1がデフォルトです。

プレハブを使用している場合、スケール1は底面からの垂直の棒の高さに相当します。

![hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png)
![hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png)

> 値が0.5の場合、物理空間で高さ全体を移動するには、仮想空間で高さの半分を移動する必要があります：
> 
> ![hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png)

> 値が2の場合、物理空間で高さ全体を移動するには、仮想空間で高さの2倍を移動する必要があります：
>
> ![hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png)
> ![hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png)

:::tip
値を下げると、ロボットアームが物理空間で高さ全体を移動するために仮想空間で必要な身体的な労力が少なくなります。
:::

## Hard limits {/* #hard-limits */}

*Hard limits* は、ロボットアームが移動を許可される**最大の高さと最小の高さを狭めます**。

この値を変更すると、Virtual scale とオフセットが内部で補正され、Hard limits の間の範囲を移動するのに、引き続き仮想空間での
全移動距離が必要になるようにします。これは *Compensate virtual scale* チェックボックスで無効にできます。

![hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png)

:::tip
ロボットアームが高く上がりすぎると思う場合は、最大の高さを下げることをおすすめします。
別の方法として、ロボットアームの固定点を物理的に低くしてから、最小の高さを上げることもできます。

ロボットアームが早く底に当たりすぎる場合は、ロボットアームの固定点を物理的に高くするか、最小の高さを上げてください。
:::

## Offsets {/* #offsets */}

*Offsets* では、位置が適用された後のロボットアームのピッチ角を調整できます。

これは移動の方向を変えるものではありません。仮想空間での移動は、物理空間でも同じ方向の移動になります。

## Safety settings {/* #safety-settings */}

:::warning
これらの設定を変更すると、ロボットアームが通常とは異なる動きをする可能性があります。注意して使用してください。
:::

### Limit movement at the bottom {/* #limit-movement-at-the-bottom */}

この安全設定は、横方向に移動できるロボットアーム向けに設計されています。

*Limit movement at the bottom* 設定は、次のことを行います。
- ロボットアームの横方向の移動を円の中に制限します。
- ロボットアームが機械の可能な最上部の高さにある場合、その円の半径は100%になります。
- ロボットアームが機械の可能な最下部の高さにある場合、その円の半径は40%になります。

これにより、ロボットアームの移動は下向きの円錐台の形に制限されます。

![hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png)

この設定はデフォルトでONです。この設定のチェックを外すと、ロボットアームは全範囲を移動できるようになります。

:::note
Hard limits を下げてもこの円錐の形は押しつぶされないため、低いリミットでも安全性は保たれます。

![hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png)
![hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png)
:::

## Twist {/* #twist */}

ひねり軸に対応したデバイスをお持ちの場合：残念ながら、DPS系ライトは位置と方向の情報にしか対応していません。
方向軸まわりの回転情報は持っていません。

そのため、*本当の「ひねり」*は実現できません。その代わりに、*シミュレートされた*ひねりの設定を有効にして、
他の利用可能な情報からひねり用のモーターを駆動できます：

- *Simulated twist from Roll* は、方向が横にどれだけ傾いているかに基づいてひねりを加えます。
- *Simulated twist from Lateral* は、位置が中心から横方向にどれだけ離れているかに基づいてひねりを加えます。

スライダーで、これらがひねりにどれだけ影響するかを調整します。負の値を設定すると、逆方向にひねることができます。

Roll と Lateral の両方のシミュレートされたひねりを組み合わせることができます。

## Rotate machine {/* #rotate-machine */}

:::warning
この設定は最も影響の大きい設定の1つであるため、**Robotics (Advanced)** タブにあります。
仮想空間と物理空間で方向が一致しなくなります。

機械の動作がおかしいと思ったら、Reset ボタンを押してください。回転が0に戻ります。
:::

Rotate machine 設定を使用すると、仮想空間でのある方向への移動が、物理空間では別の方向への移動になります。

- これにより、仮想空間での水平方向の動きを、物理空間での垂直方向の動きに変えることができます。
- また、水平向きに設置されたロボットアームを使用している場合は、この設定で空間を補正し、仮想空間と物理空間を一致させることができます。

> 値が90の場合、機械のピッチが90度回転します。
> - ロボットアームが垂直向きの場合、仮想空間で自分に近づく動きは、物理空間では下向きの動きになります（空間の方向は一致しなくなります）。
> - ロボットアームが水平向きの場合、仮想空間で自分に近づく動きは、物理空間でも自分に近づく動きになります（空間の方向が一致します）。
> 
> ![hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png)
> ![hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png)
> ![hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png)

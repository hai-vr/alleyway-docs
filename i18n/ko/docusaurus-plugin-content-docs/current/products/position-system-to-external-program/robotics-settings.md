---
sidebar_position: 50
---
import HaiLocalization from "/src/components/HaiLocalization";

# Robotics 설정

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

Robotics 탭의 설정으로 사용 중인 로봇 암의 동작을 사용자 지정할 수 있습니다.

하는 일에 따라 이 설정들을 실시간으로 조정해야 할 수도 있습니다.

## Virtual scale {/* #virtual-scale */}

*Virtual scale*은 물리 공간에서 같은 양의 움직임을 만들어 내기 위해 가상 공간에서 필요한 움직임의 양을 바꿉니다. 기본값은 1입니다.

프리팹을 사용하는 경우, 스케일 1은 바닥면에서부터 수직 막대까지의 높이에 해당합니다.

![hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_4b7fabba-b2db-4821-bbbd-1810087e59e0.png)
![hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_78baedb9-dd63-4955-a445-9b31054bea97.png)

> 값이 0.5이면, 물리 공간에서 전체 높이를 움직이기 위해 가상 공간에서 높이의 절반만큼 움직여야 합니다:
> 
> ![hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_2e9bf4f0-9870-4d13-972c-fa759d5050f7.png)

> 값이 2이면, 물리 공간에서 전체 높이를 움직이기 위해 가상 공간에서 높이의 두 배만큼 움직여야 합니다:
>
> ![hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_424bd810-29fa-4a2d-a99a-42809fd20f3a.png)
> ![hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_06f37891-cfa6-4145-bda5-f592c9427e65.png)

:::tip
값을 낮추면, 로봇 암이 물리 공간에서 전체 높이를 이동하는 데 가상 공간에서 필요한 신체적 노력이 줄어듭니다.
:::

## Hard limits {/* #hard-limits */}

*Hard limits*는 로봇 암이 움직일 수 있는 **최대 높이와 최소 높이의 범위를 좁힙니다**.

이 값을 변경하면 Virtual scale과 오프셋이 내부적으로 보정되어, Hard limits 사이의 범위를 움직이는 데 여전히 가상 공간에서
전체 이동 거리가 필요하도록 유지됩니다. 이 기능은 *Compensate virtual scale* 체크박스로 끌 수 있습니다.

![hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_71b6434e-e78b-40f6-b02f-1838e58b6acb.png)

:::tip
로봇 암이 너무 높이 올라간다고 생각되면 최대 높이를 낮추는 것을 권장합니다.
다른 방법으로, 로봇 암의 고정 지점을 물리적으로 더 낮게 옮긴 다음 최소 높이를 높일 수도 있습니다.

로봇 암이 너무 일찍 바닥에 닿는다면, 로봇 암의 고정 지점을 물리적으로 더 높게 조정하거나 최소 높이를 높이세요.
:::

## Offsets {/* #offsets */}

*Offsets*로 위치가 적용된 후 로봇 암의 피치 각도를 조정할 수 있습니다.

이는 움직임의 방향을 바꾸지 않습니다. 가상 공간에서의 움직임은 물리 공간에서도 같은 방향의 움직임이 됩니다.

## Safety settings {/* #safety-settings */}

:::warning
이 설정을 변경하면 로봇 암이 평소와 다른 움직임을 보일 수 있습니다. 주의해서 사용하세요.
:::

### Limit movement at the bottom {/* #limit-movement-at-the-bottom */}

이 안전 설정은 옆으로 움직일 수 있는 로봇 암을 위해 설계되었습니다.

*Limit movement at the bottom* 설정은 다음과 같이 작동합니다.
- 로봇 암의 측면 움직임을 원 안으로 제한합니다.
- 로봇 암이 기계가 낼 수 있는 가장 높은 위치에 있을 때, 그 원의 반지름은 100%입니다.
- 로봇 암이 기계가 낼 수 있는 가장 낮은 위치에 있을 때, 그 원의 반지름은 40%입니다.

이로써 로봇 암의 움직임은 아래를 향한 원뿔대 모양으로 제한됩니다.

![hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_368d5c87-e92d-402c-bb9a-4263050ee894.png)

이 설정은 기본적으로 켜져 있습니다. 이 설정의 체크를 해제하면 로봇 암이 전체 범위를 움직일 수 있게 됩니다.

:::note
Hard limits를 낮춰도 이 원뿔의 모양은 찌그러지지 않으므로, 낮은 한계값에서도 안전하게 유지됩니다.

![hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c8297c8b-5d38-4f69-8f4d-cce273f5aa58.png)
![hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_589b3e11-7942-4611-a98c-82114561dbc1.png)
:::

## Twist {/* #twist */}

비틀림 축을 지원하는 장치를 가지고 있다면: 안타깝게도 DPS 계열 라이트는 위치와 방향 정보만 지원하며,
방향 축을 중심으로 한 회전 정보는 없습니다.

따라서 *진정한 "비틀림"*은 구현할 수 없습니다. 대신 *시뮬레이션된* 비틀림 설정을 활성화하면
사용 가능한 다른 정보를 이용해 비틀림 모터를 구동할 수 있습니다:

- *Simulated twist from Roll*은 방향이 옆으로 얼마나 기울어졌는지에 따라 비틀림을 더합니다.
- *Simulated twist from Lateral*은 위치가 중심에서 옆으로 얼마나 떨어져 있는지에 따라 비틀림을 더합니다.

슬라이더로 이 값들이 비틀림에 미치는 영향의 크기를 조절합니다. 음수를 설정하면 반대 방향으로 비틀 수 있습니다.

Roll과 Lateral에서 오는 시뮬레이션된 비틀림을 함께 사용할 수 있습니다.

## Rotate machine {/* #rotate-machine */}

:::warning
이 설정은 가장 큰 영향을 주는 설정 중 하나이기 때문에 **Robotics (Advanced)** 탭에 있습니다.
가상 공간과 물리 공간의 방향이 더 이상 일치하지 않게 됩니다.

기계의 동작이 이상하다고 생각되면 Reset 버튼을 누르세요. 회전이 다시 0으로 설정됩니다.
:::

Rotate machine 설정을 사용하면, 가상 공간에서 한 방향으로 움직인 것이 물리 공간에서는 다른 방향의 움직임이 됩니다.

- 이를 이용해 가상 공간의 수평 움직임을 물리 공간의 수직 움직임으로 바꿀 수 있습니다.
- 또는 수평으로 놓인 로봇 암을 사용하는 경우, 이 설정으로 공간을 보정하여 가상 공간과 물리 공간이 일치하도록 할 수 있습니다.

> 값이 90이면 기계의 피치가 90도 회전합니다.
> - 로봇 암이 수직으로 놓여 있다면, 가상 공간에서 나를 향하는 움직임은 물리 공간에서 아래쪽 움직임이 됩니다(공간의 방향이 더 이상 일치하지 않음).
> - 로봇 암이 수평으로 놓여 있다면, 가상 공간에서 나를 향하는 움직임은 물리 공간에서도 나를 향하는 움직임이 됩니다(공간의 방향이 일치함).
> 
> ![hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_c7128e41-089f-441f-b185-555b6c70601f.png)
> ![hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_1f4de1a6-f149-4325-8dec-7ccbf2103bb8.png)
> ![hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png](@site/docs/products/position-system-to-external-program/img/hasm_thumbnail_3211d23b-a2f7-4d42-8385-6c01248cd1bc.png)

---
sidebar_position: 30
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 아바타 설정하기

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
소프트웨어와 프리팹은 로봇 암이 **연결된 컴퓨터**에만 필요합니다. 가상 공간의 다른 사용자에게는 필요하지 않으며,
표준 DPS 계열 라이트만 있으면 됩니다.

SPS와 같은 표준 DPS 계열 라이트를 이미 가지고 있다면, 별도의 설정 없이 바로 여러분의 로봇 암을 제어할 수 있습니다.
:::

사용하는 플랫폼이나 애플리케이션에 따라 아래 섹션 중 하나를 선택하세요:
- [Modular Avatar를 사용하는 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-modular-avatar)
- [VRCFury를 사용하는 **VRChat** Avatars SDK](#vrchat-avatars-sdk-using-vrcfury)
- [**Resonite**](#resonite)
- [**ChilloutVR**](#chilloutvr)
- [**Basis** 프레임워크로 만든 애플리케이션](#applications-built-using-the-basis-framework)

## Modular Avatar를 사용하는 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-modular-avatar */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::info
Modular Avatar가 있다면 이 방법을 권장합니다. Modular Avatar는 없지만 VRCFury가 있다면 [아래의 다른 섹션을 참고하세요](#vrchat-avatars-sdk-using-vrcfury).<br/>
**둘 중 하나는 반드시 있어야 합니다.**

*또한 SPS 라이트도 DPS 계열 라이트이므로, 이 포지션 시스템에서 작동합니다.*
:::

아바타에서:
- *Project* 탭에서 *Packages/Alleyway - Position System/Prefabs/* 폴더를 엽니다.
- *PositionSystem-VRC-MA* 프리팹을 아바타 루트에 추가합니다.

![Unity_vBn2gPNKzq.png](@site/docs/products/position-system-to-external-program/img/Unity_vBn2gPNKzq.png)

설정을 더 세부적으로 조정할 수 있으며, 다음 단계는 선택 사항입니다:
- *System* 오브젝트의 크기를 조정할 수 있습니다. 노란색 막대의 길이는 로봇 암의 전체 이동 거리와 대략 같습니다.
- 메뉴 위치를 바꾸고 싶다면 `(prefab)/System`에 *MA Menu Installer* 컴포넌트가 있습니다.
- 기본적으로 캘리브레이션 원점은 오른손에 있습니다.
    - `(prefab)/System/HandRoot`에 있는 *Armature Link* 컴포넌트를 사용해 왼손으로 바꿀 수 있습니다.
    - 주로 쓰는 손과 그렇지 않은 손 중 어느 쪽으로 정해야 할지는 분명하지 않습니다. 저는 개인적으로 주로 쓰는 손으로 설정해 두었습니다.
    - 자식 오브젝트인 *HandPalmDown*은 손바닥 아래, 손에서 대략 손 두 개 정도 떨어진 거리에 떠 있게 됩니다.

메시를 병합하는 아바타 최적화 도구를 사용한다면 다음 오브젝트를 제외하세요:
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 이 메시는 특수한 메시이므로 변환하거나 단순화해서는 안 됩니다.

## VRCFury를 사용하는 VRChat Avatars SDK {/* #vrchat-avatars-sdk-using-vrcfury */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

:::note
저는 제 프로젝트에 VRCFury를 사용하지 않으며, 그 컴포넌트들에 대해 잘 알지 못합니다. 그래도 Modular Avatar 프리팹을 바탕으로
대응하는 컴포넌트를 사용해 VRCFury 프리팹을 시험적으로 만들었습니다.

다만 VRCFury 프리팹이 올바르게 설정되었다고 보장할 수는 없습니다.

*또한 SPS 라이트도 DPS 계열 라이트이므로, 이 포지션 시스템에서 작동합니다.*
:::

아바타에서:
- *Project* 탭에서 *Packages/Alleyway - Position System/Prefabs/* 폴더를 엽니다.
- *PositionSystem-VRC-VRCFury* 프리팹을 아바타 루트에 추가합니다.

![5bbBMWuP85.png](@site/docs/products/position-system-to-external-program/img/5bbBMWuP85.png)

설정을 더 세부적으로 조정할 수 있으며, 다음 단계는 선택 사항입니다:
- *System* 오브젝트의 크기를 조정할 수 있습니다. 노란색 막대의 길이는 로봇 암의 전체 이동 거리와 대략 같습니다.
- 메뉴 위치를 바꾸고 싶다면 `(prefab)/System`에 *Full Controller* 컴포넌트가 있습니다.
- 기본적으로 캘리브레이션 원점은 오른손에 있습니다.
    - `(prefab)/System/HandRoot`에 있는 *Armature Link* 컴포넌트를 사용해 왼손으로 바꿀 수 있습니다.
    - 주로 쓰는 손과 그렇지 않은 손 중 어느 쪽으로 정해야 할지는 분명하지 않습니다. 저는 개인적으로 주로 쓰는 손으로 설정해 두었습니다.
    - 자식 오브젝트인 *HandPalmDown*은 손바닥 아래, 손에서 대략 손 두 개 정도 떨어진 거리에 떠 있게 됩니다.

메시를 병합하는 아바타 최적화 도구를 사용한다면 다음 오브젝트를 제외하세요:
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PStoEP-Encoder`
- 이 메시는 특수한 메시이므로 변환하거나 단순화해서는 안 됩니다.

## VRChat Worlds SDK {/* #vrchat-worlds-sdk */}

:::danger
🚫 **월드에 셰이더 데이터 인코더 시스템을 통합하는 것은 권장하지 않습니다.**

HMD 내의 정렬 문제를 해결하기 위해 사용자가 셰이더 머티리얼을 직접 조정해야 할 수 있기 때문입니다.
:::

월드는 지원하지 않습니다. 다만 다음 사항을 고려해 보세요:

DPS 계열 라이트는 아바타에만 국한되지 않습니다. 월드에서 로봇 암을 제어하고 싶다면,
같은 DPS 계열 라이트 설정을 사용할 수 있을지도 모릅니다.

또한 저희는 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)을 지원합니다.
자신을 위한 월드를 만들고 있다면, WebSocket으로 명령을 보내는 로그 파서를 만들 수도 있습니다.

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

Resonite는 WebSocket을 지원하므로, 이를 이용해 위치와 법선을 추출할 수 있습니다.

오브젝트에 *WebsocketClient* 컴포넌트를 만듭니다. *Websocket Text Message Sender* 노드를 사용해 텍스트 메시지를 보냅니다.
- 포트 **56247**의 URL `ws://localhost:56247/ws`에 WebSocket을 엽니다.
- 텍스트 메시지 문자열은 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system) 문서에 명시된 형식을 따라야 합니다.
- 특정 좌표 공간에서의 위치(예: 로컬 트랜스폼 또는 글로벌 트랜스폼)를 전달합니다.
- 위치와 같은 좌표 공간에서의 방향(예: Up 또는 Forward 방향 등)을 전달합니다.
- *선택적으로, 방향에 수직인 접선(예: Up 또는 Forward 방향 등)도 전달할 수 있습니다. 아직 이 정보는 사용하지 않지만, 나중에 비틀림을 제어하는 데 쓰일 수 있습니다.*

소프트웨어를 사용할 때 [WebSocket 서비스는 기본적으로 꺼져 있으므로 활성화해야 합니다](developer#websockets).

현재 바로 사용할 수 있는 ProtoFlux 아이템은 제공하지 않습니다. 구현 예시로 아래 그림을 참고하세요.

:::note
이 글을 읽고 계신다면 아마 저보다 ProtoFlux를 더 잘 아실 테니, 이 설계도에서 명백한 실수가 보인다면
그대로 따라 하지 마세요.

예를 들어, 이 처리는 로봇 암에 연결된 컴퓨터에서만 실행되어야 하지만, 현재 이 그래프에는 그런 제한이 없습니다.
:::

[![resonite_websocket.jpg](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)](@site/docs/products/position-system-to-external-program/img/resonite_websocket.jpg)

## ChilloutVR {/* #chilloutvr */}

<HaiTags>
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

:::danger
ChilloutVR 프리팹은 아바타에 추가하기가 조금 까다롭습니다. 기본 애니메이터를 저희 애니메이터와 병합해야 하는데,
이 단계를 깔끔하게 하는 방법은 저도 잘 모릅니다.

문제가 생길 수 있으니, 시도해 보실 거라면 각오를 단단히 하세요.
:::

프리팹을 시험적으로 추가해 두었습니다.

- *Project* 탭에서 *Packages/Alleyway - Position System/Prefabs/* 폴더를 엽니다.
- *PositionSystem-ChilloutVR* 프리팹을 아바타 루트에 추가합니다.
- 반드시 아바타 루트에 있어야 합니다. 프리팹 오브젝트의 **이름을 바꾸지 마세요**. 애니메이션이 이 이름에 의존합니다.

![Unity_XEqPy4mBCe.png](@site/docs/products/position-system-to-external-program/img/Unity_XEqPy4mBCe.png)

프리팹을 언팩하려면:
- 프리팹을 언팩합니다.
- HandRoot와 NeckRoot 오브젝트를 각각 손 본과 목 본으로 옮깁니다.
  - HandRoot를 주로 쓰는 손과 그렇지 않은 손 중 어느 쪽에 지정해야 할지는 분명하지 않습니다. 저는 개인적으로 주로 쓰는 손으로 설정해 두었습니다.
  - 자식 오브젝트인 *HandPalmDown*은 손바닥 아래, 손에서 대략 손 두 개 정도 떨어진 거리에 떠 있게 됩니다.
- 로컬 위치를 0으로 설정합니다.

:::note
프리팹을 언팩하지 않고 하려면, 대신 다음과 같이 하세요:
- HandRoot와 NeckRoot 오브젝트의 **복제본을 만들어** 각각 손 본과 목 본에 둡니다.
  - HandRoot를 주로 쓰는 손과 그렇지 않은 손 중 어느 쪽에 지정해야 할지는 분명하지 않습니다. 저는 개인적으로 주로 쓰는 손으로 설정해 두었습니다.
  - 자식 오브젝트인 *HandPalmDown*은 손바닥 아래, 손에서 대략 손 두 개 정도 떨어진 거리에 떠 있게 됩니다.
- 로컬 위치를 0으로 설정합니다.
- 프리팹에서 `(prefab)/System/CalibrationConstraint`를 찾습니다.
- *Position Constraint* 컴포넌트에서 컨스트레인트 소스를 새 HandRoot 오브젝트로 다시 지정합니다.
- *Aim Constraint* 컴포넌트에서 컨스트레인트 소스를 새 NeckRoot 오브젝트로 다시 지정합니다.
:::

애니메이터 설정하기:
- Project 뷰에서 `Packages/Alleyway - Position System/Internal/App-ChilloutVR/AbsolutePaths/`로 이동합니다.
- `PositionSystem-Animator-CVR-Absolute.controller` 애니메이터 컨트롤러 에셋 파일을 열고,
- 두 레이어를 파라미터 및 파라미터 값과 함께 자신의 애니메이터에 복사합니다 **(TODO: 이건 어떻게 하나요???)**.

*CVR Avatar* 컴포넌트 설정하기:
- Advanced Settings에서:
  - 파라미터 `PStoEP_Enabled`를 토글하는, *Enabled*라는 이름의 Float 타입 Toggle을 추가합니다.
  - 파라미터 `PStoEP_EnabledAndVisible`을 토글하는, *Enabled and Visible*이라는 이름의 Float 타입 Toggle을 추가합니다.
  - 파라미터 `PStoEP_BringToHand`를 토글하는, *Bring to Hand*라는 이름의 Float 타입 Toggle을 추가합니다.

선택 사항:
- *System* 오브젝트의 크기를 조정할 수 있습니다. 노란색 막대의 길이는 로봇 암의 전체 이동 거리와 대략 같습니다.

:::info[ChilloutVR 고급 사용자를 위한 추가 정보]

다음 내용은 이 프리팹을 변환하는 방법을 이해하는 데 도움이 될 것입니다.

오브젝트 구조:
- `(prefab)/System/HandRoot`의 부모를 원점 캘리브레이션에 사용할 손 중 하나로 바꿉니다.
    - 주로 쓰는 손과 그렇지 않은 손 중 어느 쪽으로 정해야 할지는 분명하지 않습니다. 저는 개인적으로 주로 쓰는 손으로 설정해 두었습니다.
    - 자식 오브젝트인 *HandPalmDown*은 손바닥 아래, 손에서 대략 손 두 개 정도 떨어진 거리에 떠 있게 됩니다.
- `(prefab)/System/NeckRoot`의 부모를 목 본으로 바꿉니다.

컴포넌트 조작/애니메이션:
- 셰이더를 사용하는 인코더 메시는 로봇 암에 연결된 컴퓨터를 가진 사람(아바타 착용자,
  또는 아이템을 스폰한 사용자)에게만 보여야 합니다.
- Unity 시스템으로 변환된 컨스트레인트와 그 애니메이션이 있습니다. ChilloutVR에서는 월드 오브젝트 프리팹 트릭을 사용하기 때문에 애니메이션 로직이 다릅니다.

ChilloutVR을 모딩할 수 있다면 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system) 사용도 검토해 보세요.
:::

## Basis 프레임워크로 만든 애플리케이션 {/* #applications-built-using-the-basis-framework */}

<HaiTags>
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

Basis 프로젝트는 수정이 가능하므로, 화면의 픽셀을 통한 데이터 추출을 사용하지 **않는** 것이 가장 쉬운 방법입니다.

대신 [WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)을 사용하세요.

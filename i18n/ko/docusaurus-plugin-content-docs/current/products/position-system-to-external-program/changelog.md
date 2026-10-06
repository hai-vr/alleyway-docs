---
title: 변경 내역
sidebar_position: 100
---
import HaiLocalization from "/src/components/HaiLocalization";

# Position System to External Program - 변경 내역

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

---

## 1.2.0

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🖥️ *프로그램이 업데이트되었습니다.*

시뮬레이션된 비틀림 추가:
- DPS 계열 데이터에는 위치와 방향 정보만 있어 이 정보가 빠져 있기 때문에, 진정한 "비틀림"은 구현할 수 없습니다.
- 측면 위치와 롤에서 도출되는 시뮬레이션된 비틀림을 추가했습니다.
- Robotics 설정에 이 시뮬레이션된 비틀림을 구성하는 Twist 섹션을 추가했습니다.

장치가 Bluetooth를 통한 시리얼 통신을 사용할 때 발생하는 문제 수정 시도:
- 초당 업데이트 횟수를 제한하는 새 설정을 추가했습니다. UI의 새 *Wireless* 탭에 있습니다.

*1.2.0-alpha.2와 비교: 체크박스가 활성화된 경우에만 전송률 제한 슬라이더를 표시합니다.*

## 1.2.0-alpha.2

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🖥️ *프로그램이 업데이트되었습니다.*

장치가 Bluetooth를 통한 시리얼 통신을 사용할 때 발생하는 문제 수정 시도:
- 초당 업데이트 횟수를 제한하는 새 설정을 추가했습니다. UI의 새 *Wireless* 탭에 있습니다.

## 1.2.0-alpha.1

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🖥️ *프로그램이 업데이트되었습니다.*

시뮬레이션된 비틀림 추가:
- DPS 계열 데이터에는 위치와 방향 정보만 있어 이 정보가 빠져 있기 때문에, 진정한 "비틀림"은 구현할 수 없습니다.
- 측면 위치와 롤에서 도출되는 시뮬레이션된 비틀림을 추가했습니다.
- Robotics 설정에 이 시뮬레이션된 비틀림을 구성하는 Twist 섹션을 추가했습니다.

## 1.1.0

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🖥️ *프로그램이 업데이트되었습니다.*

최소 높이 하드 리밋 추가:
- 로봇 암이 특정 높이 아래로 내려가지 않도록 하여 움직임의 범위를 제한합니다.
- *Compensate virtual scale*이 체크되어 있으면 Virtual scale이 내부적으로 보정되고 **또한** 오프셋이 적용되어,
  Hard limits 사이의 범위를 움직이는 데 여전히 가상 공간에서 전체 이동 거리가 필요하도록 유지됩니다.

## 1.0.2

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🌃 *프로그램은 변경되지 않았습니다.*

이번 릴리스에는 사용자에게 영향을 주는 변경 사항이 없습니다.

`package.json`에 새 설명이 추가되었으며, 이는 저장소 목록 집계 사이트에 표시됩니다.

## 1.0.1

- 🌃 *프리팹이나 셰이더는 변경되지 않았습니다.*
- 🖥️ *프로그램이 업데이트되었습니다.*

수정: 화면 전체를 어둡게 하는 포스트 프로세싱이 있는 월드에서 더 이상 데이터 디코딩이 실패하지 않습니다.
- 수정: "for Two" 월드에서 더 이상 체크섬이 실패하지 않습니다.

---

## 1.0.0

정식 릴리스입니다.

*소스 코드는 1.0.0-beta.1과 동일하며, 새 버전 번호로 다시 빌드만 했습니다.*

---

## 1.0.0-beta.1

- 🌃 *VRChat 프리팹이나 셰이더는 변경되지 않았습니다.*
- 🌕 *ChilloutVR 프리팹이 변경되었습니다. 일부 기능을 사용하려면 최신 버전으로 아바타를 다시 업로드해야 합니다.*

컴파일된 프로그램 파일에 라이선스를 포함하고, 소프트웨어에 README.txt 파일을 추가했습니다.

공개 릴리스를 위해 소프트웨어를 준비했습니다.

기타:
- 기본 VR 좌표를 (0, 0) 대신 (1, 1)로 변경했습니다.

수정 사항:
- ChilloutVR 프리팹에서 Animator 컴포넌트를 제거했습니다.
- ChilloutVR 컨스트레인트가 Unity 2022에서 저장되어 Unity 2021에서 작동하지 않던 문제를 수정했습니다.
- Rotate machine이 즉시 반영되지 않던 문제를 수정했습니다.
- 미리보기 모델을 덜 헷갈리도록 개선했습니다.

---

## 0.2.0-beta.1

💥 *호환성을 깨는 변경: 새 패키지를 설치하기 전에 이전 패키지를 제거해야 합니다. 에셋 GUID는 바뀌지 않습니다. 일부 프리팹 이름이 바뀝니다.*

🌕 *프리팹이 변경되었습니다. 일부 기능을 사용하려면 최신 버전으로 아바타를 다시 업로드해야 합니다.*

**이번 릴리스에는 호환성을 깨는 변경이 포함되어 있습니다.**

패키지 이름이 `dev.hai-vr.alleyway.position-system`으로 짧아졌습니다. 따라서 이 패키지를 설치하기 전에 이전 패키지를 제거해야 합니다.

에셋 GUID는 바뀌지 않지만, 일부 프리팹 이름이 바뀌었습니다.

이 제품은 아직 공식적으로 릴리스를 알리지 않았기 때문에 메이저 버전은 바뀌지 않습니다.

### ChilloutVR 프리팹 기반 추가 {/* #add-chilloutvr-prefab-base */}

ChilloutVR 설치 절차는 [여기에 설명되어 있습니다](./platform-setup#chilloutvr).

### 기타 {/* #other */}

호환성을 깨는 변경:
- BREAKING: 패키지 이름을 dev.hai-vr.alleyway.position-system으로 줄였습니다.
- BREAKING: 프리팹 이름을 짧게 바꿨습니다.
- BREAKING: 프리팹에서 메시 인코더 이름을 짧게 바꿨습니다.
- BREAKING: ChilloutVR과 VRChat 에셋을 별도 폴더로 분리했습니다.
- BREAKING: 많은 에셋의 이름을 바꾸고 다른 폴더로 옮겼습니다.
- 오브젝트 이름 변경으로 인해:
  - ChilloutVR 절대 경로 애니메이션을 다시 생성했습니다.
  - VRChat 상대 경로 애니메이션을 다시 생성했습니다.

기타:
- 아바타 키에 맞춰 시스템 크기를 조정할 수 있도록 미리보기 메시를 추가했습니다.
- 메뉴를 하위 메뉴 안에 넣었습니다.
- 메뉴에 아이콘이 생겼습니다.
- 이제 GitHub 릴리스에 .unitypackage 파일이 포함됩니다.


---

## 0.1.0-beta.7

🌃 *Unity 프리팹이나 셰이더는 변경되지 않았습니다.*

### ChilloutVR 프리팹 기반 추가 {/* #add-chilloutvr-prefab-base-1 */}

ChilloutVR 설치 절차는 [여기에 설명되어 있습니다](./platform-setup#chilloutvr).

### 기타 {/* #other-1 */}

- 이제 GitHub 릴리스에 .unitypackage 파일이 포함됩니다.

---

## 0.1.0-beta.6

🌕 *Unity 셰이더가 변경되었습니다. 일부 기능을 사용하려면 최신 버전으로 아바타를 다시 업로드해야 합니다.*

### 새 기능: 최대 높이 하드 리밋 옵션 추가 {/* #new-feature-add-a-maximum-height-hard-limit-option */}

Hard limits는 로봇 암이 움직일 수 있는 최대 높이를 낮춥니다.

이 값을 변경하면 Virtual scale이 내부적으로 보정되어, Hard limits 사이의 범위를 움직이는 데 여전히 가상 공간에서
전체 이동 거리가 필요하도록 유지됩니다. 이 기능은 Compensate virtual scale 체크박스로 끌 수 있습니다.

### 새 기능: 피치 오프셋 옵션 추가 {/* #new-feature-add-an-offset-pitch-option */}

오프셋으로 위치가 적용된 후 로봇 암의 피치 각도를 조정할 수 있습니다.

이는 움직임의 방향을 바꾸지 않습니다. 가상 공간에서의 움직임은 물리 공간에서도 같은 방향의 움직임이 됩니다.

### 새 기능: 로봇 암 전체를 회전하는 설정 추가 {/* #new-feature-add-a-setting-to-rotate-the-robotic-arm-entirely */}

Rotate machine 설정을 사용하면, 가상 공간에서 한 방향으로 움직인 것이 물리 공간에서는 다른 방향의 움직임이 됩니다.

- 이를 이용해 가상 공간의 수평 움직임을 물리 공간의 수직 움직임으로 바꿀 수 있습니다.
- 또는 수평으로 놓인 로봇 암을 사용하는 경우, 이 설정으로 공간을 보정하여 가상 공간과 물리 공간이 일치하도록 할 수 있습니다.

### VRCFury 프리팹 추가 {/* #add-vrcfury-prefab */}

VRCFury 설치 절차는 [여기에 설명되어 있습니다](./platform-setup#vrchat-avatars-sdk-using-vrcfury).

### 기타 {/* #other-2 */}

수정 사항:
- 이제 보이지 않는 창을 무시하므로 창 이름 검색이 더 빨라졌습니다.
- 인코더 메시에 더 이상 삭제된 Animation 컴포넌트가 남아 있지 않습니다(메시 에셋 리그의 "Animation Type"을 None으로 설정).

기타:
- **루트 PID 컨트롤러가 불안정하여 이번 릴리스에서는 비활성화했습니다.**
- 프리팹 설치에 lilToon이 필요하지 않도록, 기즈모 캘리브레이터 모델의 머티리얼을 lilToon에서 Standard로 바꿨습니다.
- 블룸을 크게 고려할 필요가 없으므로 빨간색 픽셀 대신 다시 회색 픽셀을 사용합니다. 이를 반영해 셰이더 버전을 V1.0.1로 변경했습니다.
- WebSocket은 Resonite 외에서도 사용할 수 있으므로, Resonite WebSockets라는 표현을 모두 WebSockets로 바꿨습니다.
- Debug 메뉴에서 가상 공간과 물리 공간 사이의 스케일 차이 추정치를 제공합니다. 이는 향후 작업을 위한 것으로, 가상 공간을 이동하면서
  카메라가 움직이기 시작할 때 플레이 공간의 오브젝트 위치를 조정하기 위한 준비입니다.


---

## 0.1.0-beta.5

🌃 *Unity 프리팹이나 셰이더는 변경되지 않았습니다.*

수정: 이제 컴퓨터에 ASP.NET Core 런타임이 설치되어 있지 않아도 애플리케이션을 실행할 수 있습니다.
- AspNetCore를 사용하지 않도록 WebSocket 서비스를 다시 구현했습니다.

---

## 0.1.0-beta.4

🌕 *Unity 셰이더가 변경되었습니다. 일부 기능을 사용하려면 최신 버전으로 아바타를 다시 업로드해야 합니다.*

### 새 기능: 월드 공간의 카메라 위치와 회전을 데이터에 추가 {/* #new-feature-add-world-space-camera-position-and-rotation-to-the-data */}

이제 월드 공간의 카메라 위치와 회전이 데이터에 인코딩됩니다.
이 추가 기능의 목적은 SteamVR 오버레이를 월드 공간에 고정하는 또 다른 방법을 제공하는 것입니다.

셰이더 버전이 V1.1.0으로 업데이트되었습니다.

수정 사항:
- 수정: 이제 WebSocket의 법선이 정규화됩니다.

---

## 0.1.0-beta.3

🌃 *Unity 프리팹이나 셰이더는 변경되지 않았습니다.*

### 새 기능: Resonite 지원을 위한 선택적 WebSocket 서비스 추가 {/* #new-feature-add-optional-websocket-service-for-resonite-support */}

*Resonite*에서 위치와 법선을 WebSocket으로 보내 로봇 암을 제어할 수 있습니다.
전송되는 위치는 사실상 동일한 DPS 계열 라이트를 시뮬레이션하므로, 그 결과로 나오는 로봇 암의 움직임에는 여전히 Robotics 탭의 설정이 적용됩니다.

유효한 메시지를 하나라도 받으면 모든 데이터 추출 로직보다 우선하며, 이후로는 이미지나 데이터 처리를 하지 않습니다.

자세한 내용은 [README.md의 *Websockets as an alternative input system* 섹션](https://github.com/hai-vr/position-system-to-external-program?tab=readme-ov-file#websockets-as-an-alternative-input-system)을 참고하세요.

---

## 0.1.0-beta.2

🌃 *Unity 프리팹이나 셰이더는 변경되지 않았습니다.*

### 새 기능: 로봇 암을 안정시키는 PID 컨트롤러 추가 {/* #new-feature-add-pid-controllers-to-stabilize-the-robotic-arm */}

이제 Robotics 탭에 루트 위치를 자동으로 조정하는 PID 컨트롤러 옵션과,
목표 위치의 움직임을 완화하는 또 다른 PID 컨트롤러 옵션이 있습니다.

### 새 기능: 측면 축을 제한하는 안전 설정 추가 {/* #new-feature-add-safety-setting-to-clamp-the-lateral-axes */}

이제 Robotics 탭에 측면 움직임을 원 안으로 제한하는 안전 모드가 있습니다.
원은 가장 위쪽보다 가장 아래쪽에서 더 작습니다.

### 새 기능: 사용자 지정 가상 스케일 설정 추가 {/* #new-feature-add-custom-virtual-scale-setting */}

이제 Robotics 탭에 가상 월드의 스케일을 바꾸는 슬라이더가 있습니다.
값이 클수록 물리 공간에서 같은 거리를 움직이기 위해 가상 공간에서 더 많이 움직여야 합니다.

### 기타 {/* #other-3 */}

수정 사항:
- 좌표 중 하나라도 음수이면 OpenVR 추출기가 충돌하던 문제를 수정했습니다.
- 창도 VR도 열려 있지 않은데 기본적으로 UI에 Data가 OK로 표시되던 문제를 수정했습니다.

기타:
- 루트로부터 목표까지의 거리가 3보다 크면 입력 데이터를 무시합니다.
- 앱 폴더 이름에서 물결표(~)를 제거했습니다.
- zip 파일 이름을 position-system으로 변경했습니다.

---

## 0.1.0-beta.1

### 새 기능: 표준 DPS 계열 라이트의 위치를 로봇 암에 연결 {/* #new-feature-connect-the-position-of-standard-dps-like-lights-to-a-robotic-arm */}

첫 번째 베타입니다.

이 베타에는 다음 기능을 하는 실행 파일(`.exe`)이 포함되어 있습니다:
- OpenVR 텍스처를 통해 전송된 DPS 계열 데이터를 디코딩합니다.
- 창을 통해 전송된 DPS 계열 데이터를 디코딩합니다.
- Tcode 프로토콜(SR6 및 OSR2에서 사용)을 사용하는 로봇 암이 연결된 모든 시리얼 포트로 DPS 계열 데이터를 전송합니다.

패키지에는 프리팹과 셰이더가 포함되어 있습니다:
- 프리팹은 Modular Avatar를 사용하며 메뉴를 만듭니다. 동기화 비용은 총 2비트입니다.
- 프리팹은 수동 설정이 필요하지 않습니다. 셰이더는 이미 프리팹 안에 설정되어 있습니다.

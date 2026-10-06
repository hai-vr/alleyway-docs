---
sidebar_position: 80
---
import HaiLocalization from "/src/components/HaiLocalization";

# FAQ

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

### 프로그램 설정 파일은 어디에 저장되나요? {/* #where-are-the-program-config-files-saved */}

설정 파일은 `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` 폴더에 저장됩니다.

### 현재 어떤 로봇 암 장치가 작동하나요? {/* #what-robotic-arm-devices-are-currently-working */}

현재 이 소프트웨어는 다음 로봇 암에서 작동하는 것으로 확인되었습니다:

| 제조사         | 모델    | 프로토콜     | 통신 방식  | 비고                                                                                    |
|-------------|-------|----------|--------|:--------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 시리얼 포트 |                                                                                       |
| Tempest MAx | SR6   | T-code   | 시리얼 포트 | ⚠️ 꼭 읽어 주세요:<br/>[SR6 펌웨어 패치하기](./firmware-patches#patching-the-sr6-firmware-file) |

현재 해당 장치를 보유한 기여 개발자가 없어 아직 무선 연결은 지원하지 않지만,
커스텀 펌웨어를 사용해 *Serial over Bluetooth* 연결에 성공한 OSR2+ 사용자가 최소 한 명 있으므로 무선 연결도 충분히 가능합니다.

T-code 프로토콜을 지원하는 다른 로봇 암도 작동할 수 있습니다.

### 제 로봇 암이 목록에 없습니다. 어떻게 추가하나요? {/* #my-robotic-arm-is-not-in-that-list-how-to-add-it */}

장치가 Tempest에서 설계한 것이라면, 해당 장치들은 T-code 프로토콜을 사용하므로
이미 작동할 가능성이 높습니다. 다만 직접 테스트해 보지는 않았습니다.

그렇지 않다면 다른 개발자의 도움이 필요합니다.
제가 이런 다른 로봇 암을 갖게 될 가능성은 낮기 때문에, 다른 장치에 대한 지원을 직접 추가할 수는 없습니다.

지원 추가를 시도해 볼 의향이 있는 개발자를 알고 있다면, [그 개발자에게 GitHub를 확인해 보라고 알려 주세요](https://github.com/hai-vr/position-system-to-external-program/).
- `Routine.cs`의 [**Submit()** 함수](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)부터 살펴보는 것이 좋습니다.

장치의 움직임 축이 하나뿐이라면, 향후 *Intiface*와의 연동을 추가할 수 있을지도 모릅니다.

### 무선: 로봇 암이 끊기듯 움직이거나 부드럽지 않음 {/* #wireless-the-robotic-arm-is-stuttering-or-it-is-not-smooth */}

무선 통신(Bluetooth를 통한 시리얼 통신)을 사용하던 사용자에게서 로봇 암이 비정상적으로 끊기듯 움직인다는 사례가
최소 한 건 보고되었습니다. 원인은 PC로 인한 무선 간섭이었던 것으로 보입니다.

무선 장치를 사용 중이라면, Bluetooth 동글 송신기를 USB 연장 케이블에 연결하여
PC에서 멀리 떨어뜨려 보세요.

### 무선 전송률 제한 {/* #wireless-rate-limiting */}

무선 모듈을 개발 중이거나 Bluetooth를 통한 시리얼 통신을 사용하는 특수 펌웨어를 사용 중이라면,
장치에 초당 보내는 업데이트 횟수를 줄이는 것이 좋을 수도 있고 그렇지 않을 수도 있습니다.

UI의 Wireless 탭에서 업데이트 속도를 변경할 수 있습니다. 기본 업데이트 속도는 초당 100회입니다.

초당 20회처럼 더 낮은 값이 무선 장치에는 더 적절할 수 있습니다.

### 소프트웨어의 이전 버전 {/* #older-versions-of-the-software */}

[설치](./install) 페이지에는 소프트웨어와 프리팹의 최신 버전 링크만 있습니다.

이전 버전은 [GitHub 릴리스](https://github.com/hai-vr/position-system-to-external-program/releases)에서 확인해야 합니다.

모든 릴리스와 실행 파일은 저장소의 소스 코드를 사용해 GitHub의 자동화 인프라에서 직접 컴파일됩니다.

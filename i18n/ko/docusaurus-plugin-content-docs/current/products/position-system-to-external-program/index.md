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

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Position System to External Program*은 표준 DPS 계열 라이트의 위치를 로봇 암에 연결할 수 있게 해 주는 **프리팹**과 **프로그램**입니다.

다른 사용자가 가상 공간을 통해 여러분의 로봇 암의 위치와 회전을 원격으로 제어할 수 있습니다.

:::tip
소프트웨어와 프리팹은 로봇 암이 **연결된 컴퓨터**에만 필요합니다. 가상 공간의 다른 사용자에게는 필요하지 않으며,
표준 DPS 계열 라이트만 있으면 됩니다.

SPS와 같은 표준 DPS 계열 라이트를 이미 가지고 있다면, 별도의 설정 없이 바로 여러분의 로봇 암을 제어할 수 있습니다.
:::

<HaiVideo src="./img/position-system-f-noaudio.mp4"></HaiVideo>

*이 소프트웨어는 GitHub에서 MIT 라이선스로 공개된 무료 오픈 소스 소프트웨어이므로, 직접 코드를 검토할 수 있습니다.*

## 어떻게 작동하나요? {/* #how-is-it-done */}

특수한 셰이더를 사용해 창 화면 또는 HMD에 투사되는 영상에 픽셀을 인코딩하는 방식으로 작동합니다.
그런 다음 저희 프로그램이 그 픽셀을 읽어 들입니다.

데이터 추출에는 창 캡처 및 VR 라이브 스트리밍 캡처 프로그램과 유사한 **무해한 화면 캡처** 기술을 사용합니다.
컴퓨터 프로그램을 변조하거나 실행 중인 프로세스에 개입하지 않습니다. OSC도 사용하지 않습니다.

또한:
- 월드 공간에서의 카메라 위치와 회전도 추출됩니다. 이를 이용해 SteamVR 오버레이를 월드 공간에 고정할 수 있습니다.
- 선택적으로 WebSocket 서비스를 제공하여 Resonite와 같은 가상 공간 시스템에서 로봇 암을 제어할 수 있습니다.

<HaiVideo src="./img/ILX73J2vHu-f.mp4"></HaiVideo>
*데이터 추출 방식은 화면 캡처와 유사하며, 전혀 무해합니다.*

## 호환되는 로봇 암 {/* #compatible-arms */}

현재 이 소프트웨어는 다음 로봇 암에서 작동하는 것으로 확인되었습니다:

| 제조사         | 모델    | 프로토콜     | 통신 방식  | 비고                                                                                    |
|-------------|-------|----------|--------|:--------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | 시리얼 포트 |                                                                                       |
| Tempest MAx | SR6   | T-code   | 시리얼 포트 | ⚠️ 꼭 읽어 주세요:<br/>[SR6 펌웨어 패치하기](./firmware-patches#patching-the-sr6-firmware-file) |

:::info
사용 중인 장치가 위 표에 없다면 [FAQ를 확인해 주세요](./other).

현재 해당 장치를 보유한 기여 개발자가 없어 아직 무선 연결은 지원하지 않지만,
커스텀 펌웨어를 사용해 *Serial over Bluetooth* 연결에 성공한 OSR2+ 사용자가 최소 한 명 있으므로 무선 연결도 충분히 가능합니다.

개발자라면 [도움을 주실 수 있을지도 모릅니다](other#my-robotic-arm-is-not-in-that-list-how-to-add-it).
:::

<HaiVideo src="./img/resonite-position-system-f.mp4"></HaiVideo>
*Resonite에서는 이미지 데이터 추출 대신 WebSocket을 사용해 데이터를 전송합니다.*

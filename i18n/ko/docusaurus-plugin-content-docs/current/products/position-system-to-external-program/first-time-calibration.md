---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 첫 캘리브레이션

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

프로그램을 처음 실행할 때는 제대로 작동하는지 확인하기 위한 설정이 필요합니다.

## 프로그램 실행하기 {/* #start-the-program */}

아직 설치하지 않았다면 .NET 7.0 Runtime의 "Run console apps"를 다운로드하세요 https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

그런 다음 `position-system.exe`를 실행합니다.

:::note
WebSocket을 사용하려면 [개발자 문서 페이지](./developer#websockets)를 확인하세요.
:::

## VR 캘리브레이션 {/* #vr-calibration */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} /><HaiTag requiresSteamVR={true} />
</HaiTags>

:::warning
SteamVR이 필요합니다. SteamVR을 사용하지 않는다면 창 캘리브레이션을 사용해야 합니다.

*OpenXR 개발자라면 [도움을 주실 수 있을지도 모릅니다](https://github.com/hai-vr/position-system-to-external-program/issues/1). 저는 아직 이 부분을 살펴볼 시간이 없었습니다.*
:::

실제로 진행하기 전에 아래 안내를 끝까지 읽어 주세요.

아래 캘리브레이션 과정에서는 창을 보고 제대로 작동하는지 확인합니다. 그런데 창의 내용은 VR에서 보고 있는 화면에 따라 달라집니다.
**SteamVR 데스크톱 창을 열면 화면 전체가 가려져** 투영 문제가 발생합니다. 작동 여부를 확인하는 데 SteamVR 데스크톱 창을 사용할 수는 없습니다.

첫 캘리브레이션에서는 헤드셋을 들어 올려 잠시 이마에 걸쳐 두고, 실제 모니터 화면의 창을 확인하는 방법을 추천합니다.
다음부터는 이렇게 할 필요가 없습니다.

- 소프트웨어에서 *Data calibration* 탭으로 전환합니다.
- 아직 VR에 접속하지 않았다면, 원하는 게임을 VR 모드로 실행하고 설정해 둔 아바타나 아이템을 불러옵니다.
- HMD 텍스처가 캘리브레이션되었는지 확인해야 하므로 VR에 접속한 상태여야 합니다.
- 게임 내 메뉴로 가서:
  - **Enable**을 켭니다.
  - **Bring to Hand** 버튼을 누르고 있다가 1초 후에 손을 뗍니다.
- 모든 것이 잘 되었다면 *Data calibration* 탭에 픽셀 띠가 표시됩니다.

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

이렇게 보이지 않거나 **Checksum is failing** 메시지가 빨간색으로 표시된다면:
- SteamVR 메뉴가 열려 있지 않은지 확인하세요.
- + 및 - 버튼을 클릭해 픽셀 위치를 옮겨 보세요.
- [추가 문제 해결은 다음 페이지](./fix-calibration-errors)를 확인하세요.

## 대안: 창 캘리브레이션 {/* #alternative-window-calibration */}

:::warning
창 캘리브레이션도 작동하지만, 게임이 별도의 카메라를 렌더링해야 할 가능성이 높기 때문에 권장하지 않습니다.
또한 상황에 따라서는 카메라 사용이 사생활 침해로 여겨질 수 있습니다.
:::

SteamVR을 사용하는 대신 창 캘리브레이션을 사용할 수도 있습니다.
- **SteamVR로 잘 작동한다면 이 방법은 사용하지 마세요.**
- *Data calibration*에서 Extractor preference를 *PrioritizeWindow*로 변경합니다.
- *Window name* 필드에 창 이름의 앞부분을 입력합니다.
  - 버그: 저희 프로그램이 올바른 창을 감지하지 못하면 애플리케이션을 다시 시작해야 할 수 있습니다. 이 문제는 이후 버전에서 수정될 예정입니다.
- *VRChat을 VR로 사용 중이라면 카메라를 Stream 카메라로 변경하세요.*

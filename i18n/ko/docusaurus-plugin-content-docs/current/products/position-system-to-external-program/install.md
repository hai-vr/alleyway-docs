---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 설치

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

:::tip
소프트웨어와 프리팹은 로봇 암이 **연결된 컴퓨터**에만 필요합니다. 가상 공간의 다른 사용자에게는 필요하지 않으며,
표준 DPS 계열 라이트만 있으면 됩니다.

SPS와 같은 표준 DPS 계열 라이트를 이미 가지고 있다면, 별도의 설정 없이 바로 여러분의 로봇 암을 제어할 수 있습니다.
:::

## 소프트웨어 다운로드 {/* #download-software */}

소프트웨어는 다음 위치에서 다운로드할 수 있습니다:

- **[1.2.0 소프트웨어 (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/position-system-1.2.0-executable.zip)** 다운로드

아직 설치하지 않았다면 .NET 7.0 Runtime의 "Run console apps"를 다운로드하세요 https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

*개발자라면 [GitHub에서 소프트웨어 소스 코드를 검토](https://github.com/hai-vr/position-system-to-external-program/)할 수 있습니다.*

## 프리팹 다운로드 {/* #download-prefab */}

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

프리팹을 다운로드하려면:
- **Alleyway [ALCOM 저장소](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** 를 저장소 목록에 추가합니다.
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- *Alleyway - Position System to External Program* 패키지를 프로젝트에 추가합니다.

또는 여기에서 .unitypackage 파일을 받을 수도 있습니다:

- **[1.2.0 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.2.0/dev.hai-vr.alleyway.position-system-1.2.0.unitypackage)** 다운로드

## Resonite {/* #resonite */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

현재 다운로드할 수 있는 .resonitepackage는 아직 없습니다. [ProtoFlux 설정 예시는 아바터 설정 문서](./platform-setup#resonite)를 참고하세요.

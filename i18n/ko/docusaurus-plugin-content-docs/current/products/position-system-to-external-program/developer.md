---
sidebar_position: 150
title: 개발자 문서
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 개발자 문서

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

이 웹사이트의 문서 대부분은 애플리케이션 사용자를 위한 것입니다.

개발자라면 추출 과정, 셰이더, WebSocket API, 카메라 위치 추출에 관한 기술 정보는
[GitHub의 README.md](https://github.com/hai-vr/position-system-to-external-program/)를 참고하세요.

## 다른 로봇 암 지원 추가하기 {/* #adding-support-for-other-robotic-arms */}

지원되지 않는 로봇 암을 연결하려는 개발자라면 [GitHub를 확인하세요](https://github.com/hai-vr/position-system-to-external-program/).
- `Routine.cs`의 [**Submit()** 함수](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)부터 살펴보는 것이 좋습니다.

## WebSocket {/* #websockets */}

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

*Resonite*를 사용하거나, *ChilloutVR*을 모딩하거나, Basis 프레임워크로 애플리케이션을 만들고 있다면
[WebSocket](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)을 사용하는 것이 좋습니다.

소프트웨어의 *Data calibration* 탭 하단에 있는 *Resonite WebSockets* 섹션에서 체크박스를 선택해 WebSocket 서비스를 활성화합니다.

![position-system_CUz03IfbdR.png](@site/docs/products/position-system-to-external-program/img/position-system_CUz03IfbdR.png)

[WebSocket 메시지 사양은 여기](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system)에서 확인할 수 있습니다:

> *WebSocket* 지원이 활성화되면 포트 **56247**의 URL `ws://localhost:56247/ws`에 WebSocket을 엽니다.
> 
> 해석된 위치와 법선을 나타내는 다음 문자열을 보내세요:
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ
> ```
> - *PositionX*, *PositionY*, *PositionZ*는 로컬 공간에서의 위치이며, (0, 0, 0)은 최하단 중심, (0, 1, 0)은 최상단 중심입니다.
> - *NormalX*, *NormalY*, *NormalZ*는 방향이며, 길이가 1인 벡터로 나타냅니다. 길이를 1로 맞추지 않아도 저희가 정규화하므로 상관없습니다.
> 
> 원한다면 비틀림을 정의하는 데 유용한 접선도 함께 보낼 수 있지만, 이는 선택 사항입니다:
> ```text
> PositionSystemInterpreted PositionX PositionY PositionZ NormalX NormalY NormalZ TangentX TangentY TangentZ
> ```
> - *TangentX*, *TangentY*, *TangentZ*는 접선(방향에 수직인 벡터)이며, 길이가 1인 벡터로 나타냅니다. 길이를 1로 맞추지 않아도 저희가 정규화하므로 상관없습니다.

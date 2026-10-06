---
sidebar_position: 45
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 프리팹 사용하기

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

[한 번 올바르게 캘리브레이션](first-time-calibration)하고 [로봇 암을 연결](connect)했다면, 프리팹은 다음과 같이 사용합니다.

- 메뉴의 **Enabled** 토글로 시스템을 활성화합니다.
- 메뉴의 **Enabled and Visible** 토글로 시스템을 활성화하고, 빨간색 캘리브레이션 화살표를 다른 사용자에게도 보이게 합니다.
- 메뉴의 **Bring to Hand** 버튼을 누르고 있으면 로봇 암의 최하단 중심점을 변경할 수 있습니다.
  - 메뉴 버튼에서 손을 뗀 후에는, 월드 위치가 다른 사용자에게 제대로 동기화되도록 1초 정도 손을 움직이지 마세요.
  - *Enabled and Visible* 모드가 아니라면 빨간색 캘리브레이션 화살표는 자신에게만 보입니다.

## VRChat {/* #vrchat */}

<HaiTag requiresVRChat={true} short={true} />에서는 **Expressions Menu**를 사용합니다.

## ChilloutVR {/* #chilloutvr */}

<HaiTag requiresChilloutVR={true} short={true} />에서는 메인 대형 메뉴의 **Adv Avtr** 버튼을 사용합니다.

![cvr-adv.png](@site/docs/products/position-system-to-external-program/img/cvr-adv.png)

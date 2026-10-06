---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 캘리브레이션 오류 해결

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

*Checksum is Failing* 오류가 빨간색으로 표시된다면 다음과 같은 문제가 있는지 확인하세요:

:::tip
참고로, 제대로 작동할 때는 **아래 영상**처럼 보여야 합니다:

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
:::

### 픽셀이 전혀 보이지 않음 {/* #the-pixels-are-completely-missing */}

<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 메뉴에서 Enable을 클릭했는지 확인하세요.
- 메뉴에서 Bring to Hand를 클릭했는지 확인하세요.

### 오버레이가 픽셀을 가리고 있음 {/* #an-overlay-is-obstructing-the-pixels */}

<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 왼쪽 눈과 겹치지 않도록 오버레이를 더 오른쪽으로 옮기세요.
- 왼쪽 눈 시야의 왼쪽 편에 손목 오버레이를 표시하지 마세요.

### 영역이 어긋나 있음 {/* #the-area-is-shifted */}

<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- *Reset to Defaults*를 누르고, 그래도 해결되지 않으면 Anchor와 Offset 값을 조정하세요.

### 미묘한 문제가 있는데 원인을 알 수 없음 {/* #there-is-a-subtle-issue-and-the-cause-is-unclear */}
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- + 및 - 버튼을 눌러 픽셀 위치를 옮겨 보세요.
- 다른 월드로 이동해 보세요. 특히 현재 월드에 강한 포스트 프로세싱 효과가 적용되어 있다면 효과적입니다.
- *Reset to defaults* 버튼을 눌러 보세요.

---
sidebar_position: 200
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# SR6 펌웨어 패치하기

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

## SR6 펌웨어 파일 패치하기 {/* #patching-the-sr6-firmware-file */}

SR6을 사용한다면, 버그가 발생하지 않도록 펌웨어를 패치해야 할 수 있습니다.

:::info
아래 내용은 SR6 로봇 암을 사용하는 경우에만 해당합니다.
:::

### 패치 {/* #patch */}

`SR6-Alpha5_ESP32.ino`의 429번째 줄, `SetPitchServo` 함수 안에 있는 다음 줄을:

```c
  float beta = acos((csq + 5625 - bsq)/(150*c)); // Angle between c-line and servo arm
```

다음과 같이 바꿉니다:

```c
  float beta = acos(constrain((csq + 5625 - bsq)/(150*c), -1, 1)); // Angle between c-line and servo arm
```

그런 다음 SR6 사용 설명서에 따라 펌웨어를 장치에 업로드합니다.

### 이유 {/* #reason */}

이 소프트웨어를 개발하는 중에, 펌웨어에 서보 모터로 잘못된 숫자를 보내는 버그가 있다는 사실이 발견되었습니다.

이 버그는 로봇 암에 일반적이지 않은 위치로 이동하라는 명령이 내려질 때 발생하며, 이러한 위치는 가상 공간에서 실제로 충분히 도달할 수 있습니다.

이 잘못된 명령으로 인해 서보 모터가 잘못 반응하여 극단적인 위치로 움직이게 됩니다.

그래서 SR6을 사용한다면 펌웨어를 패치할 것을 권장합니다.

<HaiVideo src="./img/firmware-f.mp4" autoWidth={false} halfWidth={true}></HaiVideo>

:::note
기술적인 이유: 1.153과 같이 1보다 큰 값이 `acos` 함수에 전달됩니다. 이 경우 NaN이 반환됩니다.

이는 아마도 펌웨어 내부의 역기구학 솔버에 오류가 있음을 의미합니다.
:::

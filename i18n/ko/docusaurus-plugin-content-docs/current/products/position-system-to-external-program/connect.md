---
sidebar_position: 43
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 로봇 암 연결하기

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

- USB로 장치를 연결합니다.
- 로봇 암의 전원을 켭니다.
- *Connect to device on serial port COM...* 을 클릭합니다.
    - 여러 시리얼 포트 장치가 연결되어 있다면, 미리 드롭다운(COM3, COM4, ...)에서 올바른 포트를 선택하세요.
    - *USB로 연결된 3D 프린터가 있다면 해당 시리얼 포트를 선택하지 않도록 주의하세요. 확실하지 않다면 3D 프린터의 전원을 끄세요.*
- 장치가 성공적으로 연결되면 *Connect to device* 버튼이 사라집니다.

<HaiVideo src="./img/position-system_oXuowuZshv.mp4"></HaiVideo>

:::note
USB가 성공적으로 연결되었더라도 로봇 암의 전원이 켜져 있는지 확인하세요.

일부 장치는 기계의 나머지 부분 전원이 꺼져 있어도 팬이 돌아가는 상태로 USB에 연결될 수 있습니다.
:::

## 문제 해결 {/* #troubleshooting */}

장치가 성공적으로 연결되면 *Connect to device* 버튼이 사라집니다.

버튼이 사라지지 않는다면 다음을 확인하세요:
- 하나의 시리얼 포트에는 한 번에 하나의 프로그램만 연결할 수 있습니다. 로봇 암을 사용하거나 테스트하기 위해 다른 소프트웨어를
  사용해 왔다면, 그 소프트웨어가 저희 소프트웨어의 연결을 방해하고 있을 수 있습니다.
  - 이 경우 해당 프로그램을 닫고 다시 버튼을 클릭해 보세요.
- 그래도 작동하지 않는다면 장치의 USB 케이블을 뽑았다가 다시 꽂아 보세요. USB 케이블을 뽑으면
  해당 장치에 대한 기존 연결이 모두 해제되므로, 다시 버튼을 클릭해 볼 수 있습니다.
- 저희 프로그램이 두 개 실행되고 있지 않은지 확인하세요. 프로그램은 하나만 실행해야 합니다.

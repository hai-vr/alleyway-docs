---
sidebar_position: 43
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 连接机械臂

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

- 通过 USB 连接你的设备。
- 打开机械臂的电源。
- 点击 *Connect to device on serial port COM...*
    - 如果你插入了多个串口设备，请事先使用下拉菜单（COM3、COM4……）选择正确的那一个。
    - *如果你有通过 USB 连接的 3D 打印机，请确保不要选中它的串口。如果不确定，请关闭 3D 打印机。*
- 如果你的设备连接成功，*Connect to device* 按钮将会消失。

<HaiVideo src="./img/position-system_oXuowuZshv.mp4"></HaiVideo>

:::note
即使 USB 已成功连接，也请确保你的机械臂已开启电源。

有些设备即使机器的其余部分仍处于断电状态，也能在风扇转动的情况下连接 USB。
:::

## 故障排除 {/* #troubleshooting */}

如果你的设备连接成功，*Connect to device* 按钮将会消失。

如果按钮没有消失，请检查以下几点：
- 同一时间只能有一个程序连接到某个串口。如果你一直在使用其他软件
  来使用或测试你的机械臂，它们可能会阻止我们的软件进行连接。
  - 在这种情况下，请关闭那些程序，然后再次尝试点击按钮。
- 如果仍然不行，你可以拔下设备的 USB 线再重新插上。拔下
  USB 线会断开与该设备的所有现有连接，之后你就可以再次尝试点击按钮。
- 确保你没有同时运行两个我们的程序。你只应打开一个程序实例。

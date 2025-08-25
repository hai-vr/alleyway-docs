---
sidebar_position: 43
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Connect the robotic arm

- Connect your device through USB.
- Power on your robotic arm.
- Click *Connect to device on serial port COM...*
    - If you have multiple serial port devices plugged in, select the correct one beforehand using the dropdown (COM3, COM4, ...).
    - *If you own a 3D printer connected over USB, please make sure you don't select its serial port. Turn off your 3D printer if you're not sure.*
- If your device has connected successfully, the *Connect to device* button will disappear.

<HaiVideo src="./img/position-system_oXuowuZshv.mp4"></HaiVideo>

:::note
Even if USB has successfully connected, make sure your robotic arm is switched ON.

Some devices can connect to USB with fans spinning even if the rest of the machine is still powered OFF.
:::

## Troubleshooting

If your device has connected successfully, the *Connect to device* button will disappear.

If it doesn't disappear, check the following:
- Only one program can connect to a given serial port at a time. If you have been using other software
  to use or test your robotic arm, they could be preventing our software from connecting.
  - In that case, close those other programs and try clicking the button again.
- If it still doesn't work, you should be able to unplug the USB cable of your device and replug it again. Unplugging
  the USB cable will cancel all existing connections to that device, so you should be able to try clicking the button again.
- Make sure that you don't have our program running twice. You should only open one instance of our program.

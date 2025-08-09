---
sidebar_position: 200
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Patching the SR6 firmware

## Patching the SR6 firmware file

If you use the SR6, you may need to patch the firmware to prevent a bug from happening.

:::info
The following only applies if you use the SR6 robotic arm.
:::

### Patch

At line 429 of `SR6-Alpha5_ESP32.ino`, in the `SetPitchServo` function, replace the following line:

```c
  float beta = acos((csq + 5625 - bsq)/(150*c)); // Angle between c-line and servo arm
```

with this:

```c
  float beta = acos(constrain((csq + 5625 - bsq)/(150*c), -1, 1)); // Angle between c-line and servo arm
```

Then, upload the firmware to your device using the instruction manual of your SR6.

### Reason

During development of this software, it was discovered that the firmware has a bug that causes an invalid number to be
sent to the servo motors.

This bug happens when the robotic arm is instructed to move to an unusual position, which could realistically be reached
in the virtual space.

This incorrect instruction will cause the servo motors to respond incorrectly by moving to an extreme position.

For this reason, if you use the SR6, I recommend you to patch the firmware.

<HaiVideo src="./img/firmware-f.mp4" autoWidth={false} halfWidth={true}></HaiVideo>

:::note
For the technical reason: A value greater than 1, such as 1.153 is passed to the `acos` function. This returns NaN.

This probably indicates that the inverse kinematics solver within the firmware has a mistake in it.
:::
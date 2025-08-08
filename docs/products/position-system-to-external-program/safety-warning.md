---
sidebar_position: 5
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# ⚠️ Safety warning

Normally, robotic arms for domestic use are traditionally controlled using mathematical algorithms that produce smooth curves.
This makes them very predictable, testable, and ensures that the motion of the robotic arm is comfortable and relatively free of haphazard motions.

However, **this is NOT the case with this software**. Instead of mathematical algorithms, the robotic arm is controlled by a shared virtual space,
which is an imperfect system.

When using a position system through a shared virtual space, **the motion of the robotic arm will not benefit from these safeties**.
Carefully consider the following risks:
- If the entity or person controlling the position of your robotic arm suffers from loss of tracking, the robotic arm may treat that loss of tracking as a position to reach.
- If the entity or person controlling the position of your robotic arm moves too fast, the robotic arm may attempt to reach that position faster than the motors are capable of.
  This will result in unexpected angles from your robotic arm during the travel. The more degrees of freedom your device has, the more likely this is going to happen.
- In addition, the firmware and hardware will be subjected to positions that may be considered unusual by traditional software, and therefore those positions may be less tested.
  These unusual positions could cause damage to your robotic arm or reveal bugs in the firmware that may compromise the expected position of the robotic arm.

If you choose to use a robotic arm in a shared virtual environment, be responsible and **communicate thoroughly to ensure a safer experience
for all parties**.

**You are solely responsible for your own personal safety.**

## ⚠️ Fire hazard

Some low-quality servos can burn out and short-circuit closed, causing parts of the robotic arm to heat up even beyond the glass transition temperature
of some 3D-printed materials. This can pose a fire hazard.

Keep an eye out on your device and **power it off when not in use**. Do not fall asleep while your device is still powered on.

:::danger
If you're going to build your own robotic arm, **do not buy any of the cheap 20kg/cm garbage red servos**. Those are notorious for burning out.

![servo_burn.jpg](img/servo_burn.jpg)
:::

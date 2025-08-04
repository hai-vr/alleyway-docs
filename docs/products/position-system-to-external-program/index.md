---
unlisted: true
title: "Position System to External Program"
---

*Position System to External Program* is a **shader** and a **program** that lets you connect the position of standard DPS-like lights
to a robotic arm.

Other users may be able to remotely control the position and rotation of your robotic arm through a shared virtual space.

:::danger
This document is a draft. This software is not yet released.
:::

## Robotic arms

As of currently, this software is known to function with the following robotic arms:

| Vendor      | Model | Protocol | Communication mode | Tested |
|-------------|-------|----------|--------------------|--------|
| Tempest MAx | SR6   | T-code   | Serial port        | ✅      |
| Tempest MAx | OSR2  | T-code   | Serial port        | ✅      |

Wireless is not yet supported, as we do not currently have contributing developers who own such a device.

*If you are a developer, you may be able to add wireless support yourself. This project is released under the MIT License.*

## ⚠️ Safety warning

Normally, robotic arms for domestic use are traditionally controlled using mathematical algorithms that produce smooth curves, which ensures that
the motion of the robotic arm is comfortable and relatively free of haphazard motions.

However, **this is NOT the case with this software**. Instead of mathematical algorithms, the robotic arm is controlled by a shared virtual world,
which is an imperfect system.

When using a position system through a shared virtual space, **the motion of the robotic arm will not benefit from these safeties**.
Carefully consider the following risks:
- If the entity controlling the position of your robotic arm suffers from loss of tracking, the robotic arm may treat that loss of tracking as a position to reach.
- If the entity controlling the position of your robotic arm moves too fast, the robotic arm may attempt to reach that position faster than the motors are capable of,
which will result in unexpected angles from your robotic arm.
- In addition, the firmware and hardware will be subjected to positions that may be considered unusual by traditional software, and therefore those positions may be less tested.
These unusual positions could cause damage to your robotic arm or reveal bugs in the firmware that may compromise the expected position of the robotic arm.

If you choose to use a robotic arm in a shared virtual environment, be responsible and **communicate thoroughly to ensure a safer experience
for all parties**.

**You are solely responsible for your own personal safety.**

## Download

TODO:

## Method

To extract data, we provide three methods:
- In VR, the data is extracted through an area located at the outer edge of your headset, which may be visible.
  - This is the recommended method in VR because it is the least privacy-intrusive method in respect to other users.
- In VR, you may also choose to extract data from a window, but this may require the use of a camera normally used for streaming,
  which can be considered privacy-intrusive 👎.
- In non-VR, you can extract data from a window.

## Integration

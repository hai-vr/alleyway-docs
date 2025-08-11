---
title: "Position System to External Program"
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

*Position System to External Program* is a **prefab** and a **program** that lets you connect the position of standard DPS-like lights
to a robotic arm.

Other users can remotely control the position and rotation of your robotic arm through the virtual space.

:::tip
Only the **computer connected** to the robotic arm needs the software and the prefab. The other users in the virtual space do not need it,
they just need a standard DPS-like light.

If they already have a standard DPS-like light such as SPS, then they can control your robotic arm, no additional setup needed from them.
:::

<HaiVideo src="./img/position-system-f-noaudio.mp4"></HaiVideo>

*The software is free and open source under the MIT License on GitHub, so you can audit it.*

## How is it done?

This is achieved by encoding pixels to the window screen or the image that is projected into the HMD using a special shader.
Our program then reads those pixels.

Data extraction is done using **harmless screen capture** techniques similar to those used by window and VR live-streaming capture programs.
There is no tampering of the computer program nor any active process. There is no OSC either.

In addition:
- The position and rotation of the camera in world space is also extracted. This could be used to pin SteamVR overlays in world space.
- This optionally exposes a WebSocket service to enable control of the robotic arm from virtual space systems like Resonite.

<HaiVideo src="./img/ILX73J2vHu-f.mp4"></HaiVideo>
*The data extraction method is similar to screen captures, which is completely harmless.*

## Compatible arms

As of currently, this software is known to function with the following robotic arms:

| Vendor      | Model | Protocol | Communication mode | Notes                                                                                              |
|-------------|-------|----------|--------------------|:---------------------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | Serial port        |                                                                                                    |
| Tempest MAx | SR6   | T-code   | Serial port        | ⚠️ Please read:<br/>[Patching the SR6 firmware](./firmware-patches#patching-the-sr6-firmware-file) |

:::info
If your device is not listed in that table above, please [check out the FAQ](./other).

Wireless is not yet supported, as we do not currently have contributing developers who own such a device.

If you are a developer, [you may be able to help](other#my-robotic-arm-is-not-in-that-list-how-to-add-it).
:::

<HaiVideo src="./img/resonite-position-system-f.mp4"></HaiVideo>
*In Resonite, data is transmitted using a WebSocket instead of image data extraction.*

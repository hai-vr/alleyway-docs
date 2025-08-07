---
title: "Position System to External Program"
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

*Position System to External Program* is a **shader** and a **program** that lets you connect the position of standard DPS-like lights
to a robotic arm.

Other users may be able to remotely control the position and rotation of your robotic arm through a shared virtual space.

:::warning
This document is a draft and may be incomplete.
:::

This is achieved by encoding pixels to the window screen or the image that is projected into the HMD, and our program then reads those pixels.<br/>
There is no modification to the computer program nor active process. There is no OSC either.

In addition:
- The position and rotation of the camera in world space is also extracted. This could be used to pin SteamVR overlays in world space.
- This optionally exposes a WebSocket service to enable direct control of the robotic arm from virtual space systems like Resonite.

## Robotic arms

As of currently, this software is known to function with the following robotic arms:

| Vendor      | Model | Protocol | Communication mode | Tested |
|-------------|-------|----------|--------------------|--------|
| Tempest MAx | SR6   | T-code   | Serial port        | ❓️     |
| Tempest MAx | OSR2  | T-code   | Serial port        | ❓      |

Wireless is not yet supported, as we do not currently have contributing developers who own such a device.

*If you are a developer, you may be able to add wireless support yourself. This project is released under the MIT License.*

## ⚠️ Safety warning

Normally, robotic arms for domestic use are traditionally controlled using mathematical algorithms that produce smooth curves, which ensures that
the motion of the robotic arm is comfortable and relatively free of haphazard motions.

However, **this is NOT the case with this software**. Instead of mathematical algorithms, the robotic arm is controlled by a shared virtual space,
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

As a reminder, only the **computer connected** to the robotic arm needs the software and the shader.

The other users in the virtual space do not need it, they just need a standard DPS-like light.

### Software

The software can be downloaded at this location:

- Download **[0.1.0-beta.5 (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/0.1.0-beta.5/position-system-0.1.0-beta.5-executable.zip)**

If you are a developer, you can [audit the software on GitHub](https://github.com/hai-vr/position-system-to-external-program/),
which is released under the MIT License.

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

### Shader

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

To download the shader prefab:
- Add the **Alleyway [ALCOM listing](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** to your repositories.
  - `https://hai-vr.github.io/alleyway-listing/index.json`
- Add the *Alleyway - Position System to External Program* package to your project.

## Install

:::warning
This document is a draft and may be incomplete.
:::

As a reminder, only the **computer connected** to the robotic arm needs the software and the shader.

The other users in the virtual space do not need it, they just need a standard DPS-like light.

This project does not provide those DPS-like lights.

### Avatar: VRChat platform, Modular Avatar

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

In the avatar:
- Add the *PositionSystemToExternalProgram-VRC-MA* prefab to your avatar root.

You may customize the setup further, the following steps are optional:
- If you want to change the menu location, there is an *MA Menu Installer* component in `(prefab)/System/MA-MenuInstaller`
- By default, the calibration origin will be on the right hand.
  - You can choose to switch it to your left hand using the *MA Bone Proxy* component located on `(prefab)/System/HandRoot`.
  - It is not obvious whether you should define it as your dominant or non-dominant hand. Personally, I have it set up to my dominant hand.
  - Its child object *HandPalmDown* will be hovering under your palm, approximately at two hands' distance to your hand.

If you use an avatar optimization tool that merges meshes, exclude this object:
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PositionSystemToExternalProgramEncoder-Mesh`
- This mesh is special and must not be converted or simplified.

### Avatar: VRChat platform, VRCFury

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
</HaiTags>

In the avatar:
- Add the *PositionSystemToExternalProgram-VRC-MA* prefab to your avatar root.

I do not have VRCFury installed, and I am not familiar enough with its components; here are the things you need to know to adapt this prefab to VRCFury:
- Probably using *Full Controller*, manage to do the following:
  - Merge the animator located within the *Animator* component with paths relative to the `(prefab)/System` object, which is in:
    - *`Packages/Alleyway - Position System to External Program/Internal/Animator/PositionSystemToExternalProgram-Animator.asset`*
  - Integrate the expression menu asset, which is in:
    - *`Packages/Alleyway - Position System to External Program/Internal/PositionSystemToExternalProgram-Menu.asset`*
  - Integrate the expression parameters asset, which is in:
    - *`Packages/Alleyway - Position System to External Program/Internal/PositionSystemToExternalProgram-Parameters.asset`*
- Probably using *Armature Link* bone reparenting function, or just through reparenting, manage to do the following:
  - Make `(prefab)/System/HandRoot` reparented to one of your hands, which will be used for calibrating the origin.
    - It is not obvious whether you should define it as your dominant or non-dominant hand. Personally, I have it set up to my dominant hand.
    - Its child object *HandPalmDown* will be hovering under your palm, approximately at two hands' distance to your hand.
  - Make `(prefab)/System/NeckRoot` reparented to your neck bone.

If you use an avatar optimization tool that merges meshes, exclude this object:
- `(prefab)/System/CalibrationConstraint/LocalOnly-Toggled/Parent-ReferenceScale/Parent-Rescaled/PositionSystemToExternalProgramEncoder-Mesh`
- This mesh is special and must not be converted or simplified.

### Avatar: Resonite

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

Resonite has support for Websockets, which can be used to extract a position and normal.

Use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

We do not currently provide a readily usable ProtoFlux item at this time.

### Avatar: ChilloutVR

<HaiTags>
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

We do not currently have installation instructions for ChilloutVR.

If you are more familiar with ChilloutVR, please reach out on the [temporary Alleyway Discord server](https://discord.gg/3VzveJQYWE).

Consult the VRCFury instructions above as a reference to what each GameObject does; it will give you an insight of how to convert this prefab.

There are constraints that need to be converted back to Unity systems, along with its animations; a prefab may be provided in the future for this purpose.

If you can modify ChilloutVR, you may also look into using [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

### Avatar: Applications built using the Basis Framework

<HaiTags>
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

Since Basis projects allow modification, the easiest way is **not** to use data extraction through pixels on the screen.

Use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system) instead.

## Run the software

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

- Start `position-system.exe`.
- Connect your device through USB.
- Click *Connect to device on serial port COM...*
  - If you have multiple serial port devices selected, select the correct one beforehand using the dropdown (COM3, COM4, ...).
  - *If you own a 3D printer connected over USB, please make sure you don't select its serial port. Turn off your 3D printer if you're not sure.*
  

:::info
If you made it this far into this draft documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

#### Method
<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

To extract data, we provide three methods:
- In VR, the data is extracted through an area located at the outer edge of your headset, which may be visible.
  - This is the recommended method in VR because it is the least privacy-intrusive method in respect to other users.
  - This requires <HaiTag requiresSteamVR={true} short={true} />.
- In VR, you may also choose to extract data from a window, but this may require the use of a camera normally used for streaming,
  which can be considered privacy-intrusive 👎.
- In non-VR, you can extract data from a window.

#### WebSockets

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

If you are using *Resonite*, or if you are modifying *ChilloutVR*, or if you are making an application built using the Basis Framework,
you should probably use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

In the *Data calibration* tab of the software, at the bottom in the *Resonite WebSockets* section, check the box to enable the WebSocket service. 

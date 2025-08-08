---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Program

:::warning
**This document is a draft and may be incomplete.**

This application is planned for release sometime in August, so check this documentation again in a few days.
:::

## Start the program

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

Then, start `position-system.exe`.

## Start your game

- If you aren't in VR already, start the game of your choice in VR mode and load the avatar or item that you have set up.
- You should be in VR mode, because we need to make sure the HMD texture is calibrated.
- Go to your in-game menu and:
    - Toggle **Enable** ON.
    - Hold the **Bring to Hand** button down.

If everything went well, the left eye of the HMD should now have a strip of pixels displayed within it.

TODO: Add illustration.

## Calibrate the data

This only needs to be done once.

If you use XSOverlay or OVR Toolkit:
- Open an overlay window to our program.
- Switch to the *Data calibration* tab.
- TODO

If you do not:
- Go out of VR for a bit and **do not enter the SteamVR menu**. You must have the game active in the foreground of the VR headset.
- In our program, switch to the *Data calibration* tab.
- TODO

## Drive the robotic arm

- Connect your device through USB.
- Power on your robotic arm.
- Click *Connect to device on serial port COM...*
    - If you have multiple serial port devices selected, select the correct one beforehand using the dropdown (COM3, COM4, ...).
    - *If you own a 3D printer connected over USB, please make sure you don't select its serial port. Turn off your 3D printer if you're not sure.*

:::info
If you made it this far into this draft documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

## Method

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

## WebSockets

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

If you are using *Resonite*, or if you are modifying *ChilloutVR*, or if you are making an application built using the Basis framework,
you should probably use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

In the *Data calibration* tab of the software, at the bottom in the *Resonite WebSockets* section, check the box to enable the WebSocket service.

### Where are the program config files saved?

The config files are saved in the `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` folder.
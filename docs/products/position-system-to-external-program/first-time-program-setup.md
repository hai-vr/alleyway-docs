---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# First time calibration

:::warning
**This document is a draft and may be incomplete.**

This application is planned for release sometime in August, so check this documentation again in a few days.
:::

When starting the program for the first time, you will need to set it up to verify that it works.

## Start the program

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

Then, start `position-system.exe`.

## Calibrate input

Please look into one of the following sections:
- Calibrate for [**VR** usage](#vr-calibration).
- Calibrate in [**Windowed** usage](#windowed-calibration) (not recommended if you have VR).
- Calibrate for [**WebSockets** usage](#websockets).

## VR calibration

<HaiTags>
<HaiTag requiresVRChat={true} short={true} /><HaiTag requiresChilloutVR={true} short={true} /><HaiTag requiresSteamVR={true} />
</HaiTags>

:::warning
This requires SteamVR. If you don't use SteamVR, you'll need to use the Windowed calibration.

*If you're an OpenXR developer, [you may be able to help](https://github.com/hai-vr/position-system-to-external-program/issues/1). I haven't had time to look into this yet.*
:::

You should read the entirety of those following instructions before actually doing it.

The following calibration action involves looking at a window to check if it works. However, the contents of the window depend on what you see in VR.
**Opening the SteamVR desktop window will obscure the entire screen** and cause a projection issue. You can't use the SteamVR desktop window to check if it works.

My recommendation for this first time calibration is to check the desktop window by lifting your headset so that it temporarily sits on your forehead.

- In the software, switch to the *Data calibration* tab.
- If you aren't in VR already, start the game of your choice in VR mode and load the avatar or item that you have set up.
- You should be in VR, because we need to make sure the HMD texture is calibrated.
- Go to your in-game menu and:
  - Toggle **Enable** ON.
  - Hold the **Bring to Hand** button down.
- If everything went well, you should see a strip of pixels on the *Data calibration* tab.

### Troubleshooting

## Windowed calibration

:::warning
If you have a VR headset, it is not recommended to start with Windowed calibration.

Calibrating while Windowed is different from calibrating while in VR.
:::

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
</HaiTags>

If you are using *Resonite*, or if you are modifying *ChilloutVR*, or if you are making an application built using the Basis framework,
you should probably use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

In the *Data calibration* tab of the software, at the bottom in the *Resonite WebSockets* section, check the box to enable the WebSocket service.

:::info
If you made it this far into this documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

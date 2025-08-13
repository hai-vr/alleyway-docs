---
sidebar_position: 40
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# First time calibration

When starting the program for the first time, you will need to set it up to verify that it works.

## Start the program

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

Then, start `position-system.exe`.

:::note
If you want to use WebSockets, please check the [Developer documentation page](./developer#websockets)
:::

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

My recommendation for this first time calibration is to check your actual monitor screen window by lifting your headset so that it temporarily sits on your forehead.
You don't have to do this again next time.

- In the software, switch to the *Data calibration* tab.
- If you aren't in VR already, start the game of your choice in VR mode and load the avatar or item that you have set up.
- You should be in VR, because we need to make sure the HMD texture is calibrated.
- Go to your in-game menu and:
  - Toggle **Enable** ON.
  - Hold the **Bring to Hand** button down and release it after a second.
- If everything went well, you should see a strip of pixels on the *Data calibration* tab.

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

If it doesn't look like this, or if the message **Checksum is failing** appears in red, then:
- Make sure your SteamVR menu is not open.
- Click the + and - buttons to shift the pixels around.
- Check out the [next page for further troubleshooting](./fix-calibration-errors).

## Alternative: Window calibration

:::warning
Window calibration works, but it is not recommended because the game will likely need to render another camera;
also, in some contexts, using a camera can be considered privacy-intrusive.
:::

Alternatively to using SteamVR, you can also use Window calibration.
- **Don't do this if SteamVR works out for you.**
- In *Data calibration*, change the Extractor preference to *PrioritizeWindow*.
- In the *Window name* field, type the start of the window name.
  - BUG: You may need to restart the application if our program fails to detect the correct window. This will be fixed in a later version.
- *If you use VRChat and you are in VR, change the camera to Stream camera.*

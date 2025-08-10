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
  - Hold the **Bring to Hand** button down.
- If everything went well, you should see a strip of pixels on the *Data calibration* tab.

<div className="row">
    <div className="col col--6 margin-bottom--lg">
        <div className="card">
            <div className="card__body">
<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
<p>
    **This is what you should be seeing.**

    If it doesn't look like this, please check the [next page](./fix-calibration-errors).
</p>
            </div>
        </div>
    </div>
</div>
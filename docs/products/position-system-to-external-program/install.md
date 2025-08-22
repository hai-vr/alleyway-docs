---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Install

:::tip
Only the **computer connected** to the robotic arm needs the software and the prefab. The other users in the virtual space do not need it,
they just need a standard DPS-like light.

If they already have a standard DPS-like light such as SPS, then they can control your robotic arm, no additional setup needed from them.
:::

## Download software

The software can be downloaded at this location:

- Download **[1.1.0 software (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.1.0/position-system-1.1.0-executable.zip)**

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

*You can [audit the software source code on GitHub](https://github.com/hai-vr/position-system-to-external-program/) if you are a developer.*

:::info
If you made it this far into this documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

## Download prefab

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

To download the prefab:
- Add the **Alleyway [ALCOM listing](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** to your repositories.
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- Add the *Alleyway - Position System to External Program* package to your project.

Alternatively, you could get the .unitpackage file here:

- Download **[1.1.0 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/1.1.0/dev.hai-vr.alleyway.position-system-1.1.0.unitypackage)**

## Resonite

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
</HaiTags>

There is currently no .resonitepackage for download yet. Read the [avatar setup documentation for a possible ProtoFlux setup](./platform-setup#resonite). 
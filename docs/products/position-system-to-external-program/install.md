---
sidebar_position: 10
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Install

As a reminder, only the **computer connected** to the robotic arm needs the software and the shader.

The other users in the virtual space do not need it, they just need a standard DPS-like light. This project does not provide those DPS-like lights.

:::warning
**This document is a draft and may be incomplete.**

This application is planned for release sometime in August, so check this documentation again in a few days.
:::

## Download software

The software can be downloaded at this location:

- Download **[0.2.0-beta.1 software (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/0.2.0-beta.1/position-system-0.2.0-beta.1-executable.zip)**

If you don't have it already, download .NET 7.0 Runtime "Run console apps" https://dotnet.microsoft.com/en-us/download/dotnet/7.0/runtime

You can [audit the software source code on GitHub](https://github.com/hai-vr/position-system-to-external-program/) if you are a developer.

## Download shader and prefab

<HaiTags>
<HaiTag requiresVRChat={true} short={true} />
<HaiTag requiresChilloutVR={true} short={true} />
</HaiTags>

To download the shader prefab:
- Add the **Alleyway [ALCOM listing](vcc://vpm/addRepo?url=https://hai-vr.github.io/alleyway-listing/index.json)** to your repositories.
    - `https://hai-vr.github.io/alleyway-listing/index.json`
- Add the *Alleyway - Position System to External Program* package to your project.

Alternatively, you could get the .unitpackage file here:

- Download **[0.2.0-beta.1 .unitypackage (GitHub)](https://github.com/hai-vr/position-system-to-external-program/releases/download/0.2.0-beta.1/dev.hai-vr.alleyway.position-system-0.2.0-beta.1.unitypackage)**

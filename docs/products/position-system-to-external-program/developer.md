---
sidebar_position: 150
title: Developer docs
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Developer documentation

All the documentation of this website is meant for users of the application, not developers.

If you are a developer, you should consult the [README.md on GitHub](https://github.com/hai-vr/position-system-to-external-program/)
for technical information about the extraction process, the shader, the WebSockets API, and the camera position extraction.

:::info
If you made it this far into this documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

## WebSockets

<HaiTags>
<HaiTag requiresResonite={true} short={true} />
<HaiTag requiresBasis={true} short={true} />
</HaiTags>

If you are using *Resonite*, or if you are modifying *ChilloutVR*, or if you are making an application built using the Basis framework,
you should probably use [WebSockets](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).

In the *Data calibration* tab of the software, at the bottom in the *Resonite WebSockets* section, check the box to enable the WebSocket service.

You can find the [WebSockets message specification here](https://github.com/hai-vr/position-system-to-external-program/?tab=readme-ov-file#websockets-as-an-alternative-input-system).
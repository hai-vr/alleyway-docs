---
sidebar_position: 80
---

# FAQ

### Where are the program config files saved?

The config files are saved in the `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` folder.

### What robotic arm devices are currently working?

As of currently, this software is known to function with the following robotic arms:

| Vendor      | Model | Protocol | Communication mode | Notes                                                                                              |
|-------------|-------|----------|--------------------|:---------------------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | Serial port        |                                                                                                    |
| Tempest MAx | SR6   | T-code   | Serial port        | ⚠️ Please read:<br/>[Patching the SR6 firmware](./firmware-patches#patching-the-sr6-firmware-file) |

Wireless is not yet supported, as we do not currently have contributing developers who own such a device.

Other robotic arms that support the T-code protocol may be supported.

### My robotic arm is not in that list. How to add it?

If your device was designed by Tempest, it will likely work already because <!--UNKNOWN-PRONOUN-->their devices
use the T-code protocol. I have not tested this.

Otherwise, you're going to need the help of another developer to do this.
I cannot add support for other devices myself as it's unlikely I will own other robotic arms like this.

If you know of a developer willing to try adding support, [let them check out the GitHub](https://github.com/hai-vr/position-system-to-external-program/).
- [The **Submit()** function](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs) in `Routine.cs` is probably a good place to start.

If your device only has one axis of motion, it might be possible to add integration with *Intiface* sometime in the future.

:::info
If you made it this far into this documentation, you may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

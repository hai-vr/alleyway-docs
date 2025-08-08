---
title: Changelog
sidebar_position: 100
---
# Position System to External Program - Changelog

---

## 0.1.0-beta.5

*🌃 No change in Unity prefab or shader.*

Fix application can now be started without having the ASP.NET Core runtime installed on the computer.
- Reimplement WebSockets service without using AspNetCore.

---

## 0.1.0-beta.4

*🌕 Unity Shader changed. Avatar should be reuploaded using the newest version to benefit from some features.*

### New feature: Add world space camera position and rotation to the data.

The world space camera position and rotation are now encoded in the data.
The aim of this addition is to enable an additional way to pin SteamVR overlays in world space.

The shader version has been updated to V1.1.0.

Fixes:
- Fix WebSockets normals are now normalized.

---

## 0.1.0-beta.3

*🌃 No change in Unity prefab or shader.*

### New feature: Add optional WebSocket service for Resonite support.

The robotic arm can be controlled by sending the position and normal to a WebSocket from *Resonite*.
The resulting robotic arm motion is still subject to the settings from the Robotics tab, as the position being sent effectively simulates the same DPS-like lights.

If any valid message is received, this overrides all data extraction logic; there will be no further image or data processing.

For more details, see the [*Websockets as an alternative input system* section in the README.md](https://github.com/hai-vr/position-system-to-external-program?tab=readme-ov-file#websockets-as-an-alternative-input-system).

---

## 0.1.0-beta.2

*🌃 No change in Unity prefab or shader.*

### New feature: Add PID controllers to stabilize the robotic arm.

The Robotics tab now has an option for a PID controller that auto-adjusts the root position
and another PID controller to dampen the target position.

### New feature: Add safety setting to clamp the lateral axes.

The Robotics tab now has a safety mode that limits the lateral movement to a circle.
The circle is shorter at the bottommost than at the topmost.

### New feature: Add custom virtual scale setting.

The Robotics tab now has sliders to change the scale of the virtual world.
A larger value means it takes more travel in the virtual space to cause the same amount of travel in the physical space.

### Other

Fixes:
- Fix OpenVR extractor was crashing if any coordinate was negative.
- By default, the UI no longer shows that the Data is OK even though neither the window nor VR was open.

Other:
- If the distance of the target from the root is larger than 3, input data is ignored.
- Remove tilde from app folder name.
- Change zip name to position-system.

---

## 0.1.0-beta.1

### New feature: Connect the position of standard DPS-like lights to a robotic arm.

This is the initial beta.

This beta contains an executable (`.exe`) that can:
- Decode DPS-like data transmitted through the OpenVR texture.
- Decode DPS-like data transmitted through a Window.
- Submit DPS-like data to any serial port connecting a robotic arm that uses the Tcode protocol (used by SR6 and OSR2).

The package contains a prefab and a shader:
- The prefab uses Modular Avatar and creates a menu. It has a total synced cost of 2 bits.
- The prefab does not require any manual setup. The shader is already setup within the prefab.
---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Fix calibration errors

:::info
You may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

If the error *Checksum is Failing* appears in red, check the following possible issues:

:::tip
For reference, **this video below** is what you should be seeing when it works:

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
:::

### The pixels are completely missing

<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- Check that you clicked Enable in the menu.
- Check that you clicked Bring to Hand in the menu.

### An overlay is obstructing the pixels

<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- Move the overlay more to the right to avoid it overlapping with your left eye.
- Avoid displaying wrist overlays on the left side of the field of view of your left eye.

### The area is shifted

<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- Press *Reset to Defaults*, and if it doesn't fix it, tweak the Anchor and Offset values.

### There is a subtle issue, and the cause is unclear
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
    
- Try pressing the + and - buttons to shift the pixels around.
- Try changing to a different world, especially if your current world has strong post-processing effects.
- Try pressing the *Reset to defaults* button.

:::info
You may want to know there is a **new temporary Discord server** here for early troubleshooting:
https://discord.gg/3VzveJQYWE
:::

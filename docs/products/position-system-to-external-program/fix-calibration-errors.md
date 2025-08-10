---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";

# Fix calibration errors

If the error *Checksum is Failing* appears in red, check the following:

<div className="row">
    <div className="col col--6 margin-bottom--lg">
        <div className="card">
            <div className="card__body">
<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
<p>
    The pixels are completely missing:
    - Check that you clicked Enable in the menu.
    - Check that you clicked Bring to Hand in the menu.
</p>
            </div>
        </div>
    </div>
    <div className="col col--6 margin-bottom--lg">
        <div className="card">
            <div className="card__body">
<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
<p>
    An overlay is obstructing the pixels:
    - Move the overlay more to the right, to avoid it overlapping with your left eye.
    - Avoid displaying wrist overlays on the left side of the field of view of your left eye.
</p>
            </div>
        </div>
    </div>
    <div className="col col--6 margin-bottom--lg">
        <div className="card">
            <div className="card__body">
<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
<p>
    The pixels are shifted:
    - Press *Reset to Defaults*, and if it doesn't fix it, tweak the Anchor and Offset values.
</p>
            </div>
        </div>
    </div>
    <div className="col col--6 margin-bottom--lg">
        <div className="card">
            <div className="card__body">
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
<p>
    There is a subtle issue, and the cause is unclear:
    - Try pressing the + and - buttons to shift the pixels around.
    - Try changing to a different world, especially if your current world has strong post-processing effects.
    - Try pressing the *Reset to defaults* button.
</p>
            </div>
        </div>
    </div>
</div>

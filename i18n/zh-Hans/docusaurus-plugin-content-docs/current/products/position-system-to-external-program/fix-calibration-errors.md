---
sidebar_position: 41
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 修复校准错误

<HaiLocalization languages={['en', 'ja', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

如果红色显示 *Checksum is Failing* 错误，请检查以下可能的问题：

:::tip
作为参考，正常工作时你应该看到的是**下面这个视频**中的画面：

<HaiVideo src="./img/yEUYgrVMAS-f-OK.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>
:::

### 像素完全不显示 {/* #the-pixels-are-completely-missing */}

<HaiVideo src="./img/yEUYgrVMAS-f-MISSING.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 检查你是否在菜单中点击了 Enable。
- 检查你是否在菜单中点击了 Bring to Hand。

### 有叠加层遮挡了像素 {/* #an-overlay-is-obstructing-the-pixels */}

<HaiVideo src="./img/yEUYgrVMAS-f-OBSTRUCTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 将叠加层向右移动一些，避免它与你的左眼视野重叠。
- 避免在左眼视野的左侧显示手腕叠加层。

### 区域发生了偏移 {/* #the-area-is-shifted */}

<HaiVideo src="./img/yEUYgrVMAS-f-SHIFTED.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 按下 *Reset to Defaults*，如果仍未解决，请调整 Anchor 和 Offset 的值。

### 存在细微问题，且原因不明 {/* #there-is-a-subtle-issue-and-the-cause-is-unclear */}
<HaiVideo src="./img/yEUYgrVMAS-f-SUBTLE.mp4" autoWidth={false} halfWidth={true} loop={true}></HaiVideo>

- 尝试按 + 和 - 按钮来移动像素。
- 尝试切换到其他世界，尤其是当你当前所在的世界有强烈的后期处理效果时。
- 尝试按下 *Reset to defaults* 按钮。

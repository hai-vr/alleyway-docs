---
sidebar_position: 43
---
import {HaiTags} from "/src/components/HaiTags";
import {HaiTag} from "/src/components/HaiTag";
import {HaiVideo} from "/src/components/HaiVideo";
import HaiLocalization from "/src/components/HaiLocalization";

# 連接機械手臂

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

- 透過 USB 連接你的裝置。
- 開啟機械手臂的電源。
- 點擊 *連接到序列埠 COM... 上的裝置*
    - 如果你插入了多個序列埠裝置，請事先使用下拉式選單（COM3、COM4……）選擇正確的那一個。
    - *如果你有透過 USB 連接的 3D 印表機，請確保不要選到它的序列埠。如果不確定，請關閉 3D 印表機。*
- 如果你的裝置連線成功，*連接到序列埠……上的裝置* 按鈕將會消失。

<HaiVideo src="./img/position-system_oXuowuZshv.mp4"></HaiVideo>

:::note
即使 USB 已成功連線，也請確保你的機械手臂已開啟電源。

有些裝置即使機器的其餘部分仍處於斷電狀態，也能在風扇轉動的情況下連接 USB。
:::

## 疑難排解 {/* #troubleshooting */}

如果你的裝置連線成功，*連接到序列埠……上的裝置* 按鈕將會消失。

如果按鈕沒有消失，請檢查以下幾點：
- 同一時間只能有一個程式連線到某個序列埠。如果你一直在使用其他軟體
  來使用或測試你的機械手臂，它們可能會阻止我們的軟體進行連線。
  - 在這種情況下，請關閉那些程式，然後再次嘗試點擊按鈕。
- 如果仍然不行，你可以拔下裝置的 USB 線再重新插上。拔下
  USB 線會中斷與該裝置的所有現有連線，之後你就可以再次嘗試點擊按鈕。
- 確保你沒有同時執行兩個我們的程式。你只應開啟一個程式執行個體。

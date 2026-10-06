---
sidebar_position: 80
---
import HaiLocalization from "/src/components/HaiLocalization";

# FAQ

<HaiLocalization languages={['en', 'ja', 'ko', 'zh-Hans', 'zh-Hant']} applicationIsLocalized={true} />

### プログラムの設定ファイルはどこに保存されますか？ {/* #where-are-the-program-config-files-saved */}

設定ファイルは `C:/Users/user_name/AppData/Roaming/PositionSystemToExternalProgram/` フォルダーに保存されます。

### 現在どのロボットアームが動作しますか？ {/* #what-robotic-arm-devices-are-currently-working */}

現在、このソフトウェアは以下のロボットアームで動作することが確認されています：

| ベンダー        | モデル   | プロトコル    | 通信方式     | 備考                                                                                     |
|-------------|-------|----------|----------|:---------------------------------------------------------------------------------------|
| Tempest MAx | OSR2+ | T-code   | シリアルポート |                                                                                        |
| Tempest MAx | SR6   | T-code   | シリアルポート | ⚠️ 必ずお読みください：<br/>[SR6ファームウェアのパッチ](./firmware-patches#patching-the-sr6-firmware-file) |

該当するデバイスを所有している開発協力者が現在いないため、ワイヤレスにはまだ対応していません。ただし、
カスタムファームウェアを使って *Serial over Bluetooth* での接続に成功したOSR2+ユーザーが少なくとも1人いるため、ワイヤレス対応は十分に可能です。

T-codeプロトコルに対応した他のロボットアームも動作する可能性があります。

### 自分のロボットアームがリストにありません。どうすれば追加できますか？ {/* #my-robotic-arm-is-not-in-that-list-how-to-add-it */}

お使いのデバイスがTempestによって設計されたものであれば、同社のデバイスはT-codeプロトコルを使用しているため、
おそらくすでに動作します。ただし、私はテストしていません。

そうでない場合は、別の開発者の協力が必要になります。
私がこのような他のロボットアームを所有することはなさそうなので、私自身が他のデバイスへの対応を追加することはできません。

対応の追加に挑戦してくれる開発者をご存じでしたら、[その方にGitHubを見てもらってください](https://github.com/hai-vr/position-system-to-external-program/)。
- `Routine.cs` にある [**Submit()** 関数](https://github.com/hai-vr/position-system-to-external-program/blob/main/application-loop/Routine.cs)から始めるのがよいでしょう。

お使いのデバイスの可動軸が1つだけの場合は、将来的に *Intiface* との連携を追加できる可能性があります。

### ワイヤレス：ロボットアームがカクつく、または動きが滑らかでない {/* #wireless-the-robotic-arm-is-stuttering-or-it-is-not-smooth */}

ワイヤレス通信（Bluetooth経由のシリアル通信）を使用していたユーザーから、ロボットアームが異常にカクつくという報告が
少なくとも1件ありました。原因は、PCによる何らかのワイヤレス干渉だったようです。

ワイヤレスデバイスを使用している場合は、BluetoothドングルをUSB延長ケーブルに取り付けて、
PCから離してみてください。

### ワイヤレスのレート制限 {/* #wireless-rate-limiting */}

ワイヤレスモジュールを開発している場合や、Bluetooth経由のシリアル通信を使用する特殊なファームウェアを使用している場合は、
デバイスに毎秒送信される更新の回数を減らしたほうがよいこともあれば、そうでないこともあります。

UIの Wireless タブで、更新レートを変更できます。デフォルトでは、更新レートは毎秒100回です。

毎秒20回など、より低い値のほうがワイヤレスデバイスには適している場合があります。

### ソフトウェアの旧バージョン {/* #older-versions-of-the-software */}

[インストール](./install)のページには、ソフトウェアとプレハブの最新バージョンへのリンクしかありません。

旧バージョンについては、[GitHubのリリース](https://github.com/hai-vr/position-system-to-external-program/releases)をご覧ください。

すべてのリリースと実行ファイルは、リポジトリのソースコードからGitHubの自動化インフラによって直接コンパイルされています。

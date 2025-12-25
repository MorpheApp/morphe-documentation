# Frequently asked questions

Please read them before asking questions that have been asked too many times.

## 2 Is Morphe available on iOS or TV?

Morphe is a patcher for Android apps. Android is very different from iOS. Therefore, Morphe is not available on iOS. The nearest equivalent to Morphe on iOS is [Theos](https://theos.dev/). If your TV runs Android, it may be possible to use Morphe.

## 3 How to get Morphe?

Morphe is a patcher for Android apps. Getting Morphe means patching your app. To patch your apps, download Morphe Manager from [Morphe.software](https://morphe.software) and Morphe CLI from [GitHub](https://github.com/MorpheApp/morphe-cli).

## 4 Does Morphe support non-rooted devices?

Yes! Morphe supports both non-root and rooted devices.

## 6 How can I help?

Since we are an open-source community and depend on outside help, you can always check out [our GitHub repositories](https://github.com/MorpheApp) and contribute to Morphe by creating an issue or pull request.

Additional, [financial donations](https://morphe.software/donate) are always welcomed.

## 7 Does Morphe always stay up to date with X?

Morphe Patcher allows you to use patches on any app version. However, please note that patches may not work if you're not using the versions suggested by Morphe Manager.

## 9 Where to get (full) APKs

You can get (full) APKs from sites such as [APKMirror](https://www.apkmirror.com/) or [APKPure](https://apkpure.net/de). An APK ends with the extension `.apk`.

If only split apks are available (`apkm` or `xapk` files), then tools like [AntiSplit M](https://github.com/AbdurazaaqMohammed/AntiSplit-M) can convert `apkm`/`xapk` of your device architecture to regular `apk` for use with Morphe Manager.

## 10 Capture logs 

1. (Only if the setting exists) Turn on `Miscellaneous > Debugging > Debug logging` in the settings (Ensure you have included the `Enable debugging` patch).  
2. Install the [Android developer tools](https://developer.android.com/tools/releases/platform-tools) on a computer, open a command prompt, and capture the logs using the command `adb logcat | grep 'morphe\|AndroidRuntime` to log both Morphe and crash logs. To save the logs to a file use  `adb logcat | grep 'morphe\|AndroidRuntime' > logs.txt`
3. Alternatively, you can use any Android app capable of [capturing logs](https://play.google.com/store/apps/details?id=com.dp.logcatapp) (to use these apps a one time setup is required using a computer and ADB).
4. Alternatively, in YouTube you can copy the most recent logs directly from the Debug settings menu (due to clipboard limitations the log is limited to the most recent log data). No ADB or computer setup is required. Crash logs can only be collected using ADB. 

## 12 Where to get microG GmsCore?

If you patched your app with the `GmsCore support` patch, opening your app will redirect you automatically to the correct download page.

## 13 Is Morphe affiliated with ReVanced?

Morphe is not affiliated with ReVanced. Morphe was created by a team of former ReVanced developers and contributors.

## 14 How to update patched apps?

To update a patched app, you need to patch and install the app again. 

Patch versions are completely different from the app version, and newer patches can exist even if the app version is the same as your currently patched app.

## 15 How do I backup my YouTube Morphe settings?

Morphe personalized settings are stored as copy paste text.

Navigate to: `Settings > Morphe > Miscellaneous > Import / Export`

Press the copy button to copy your settings to the clipboard. Paste your settnngs somewhere safe to save (Note app, email message, etc).

To restore your settings, paste your settings into the same `Import / Export` Morphe menu and press `Import`.

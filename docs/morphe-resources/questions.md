# Frequently asked questions

Please read them before asking questions that have been asked too many times.

## 1. What is Morphe?

Morphe is a patcher for Android apps. You can use it to patch apps and have extra features and customizability. Currently, Morphe has patches for YouTube and YouTube Music.

## 2. How to get Morphe?

[Download Morphe](https://morphe.software/download) and follow the prompts to patch your app. Alternatively, you can follow the [Morphe CLI documentation](https://github.com/MorpheApp/morphe-cli/tree/main/docs) to use Morphe CLI.

## 3. Does Morphe support non-rooted devices?

Yes! Morphe supports non-root and rooted devices.

## 4. Is Morphe available on iOS or TV?

Morphe is a patcher for Android apps. Android is very different from iOS so it is not available on iOS. If your TV runs Android, it may be possible to use Morphe.

## 5. How can I help?

Since we are an open-source community and depend on outside help, you can always check out [our GitHub repositories](https://github.com/MorpheApp) and contribute to Morphe by creating an issue or pull request. You can also help with translations on [Crowdin](https://translate.morphe.software).

Additionaly, [financial donations](https://morphe.software/donate) are always welcome.

## 6. Does Morphe always stay up to date with X?

Morphe Patcher allows you to use patches on any app version. However, please note that patches may not work if you're not using the versions suggested by Morphe Manager.

## 7. Where to get (full) APKs

You can get (full) APKs from sites such as [APKMirror](https://www.apkmirror.com/) or [APKPure](https://apkpure.net/de). An APK ends with the extension `.apk`.

If only split apks are available (`apkm` or `xapk` files), then tools like [AntiSplit M](https://github.com/AbdurazaaqMohammed/AntiSplit-M) can convert an `apkm`/`xapk` of your device architecture to a regular `apk` for use with Morphe Manager.

## 8. Where to get microG GmsCore?

If you patched your app with the `GmsCore support` patch, opening your app will redirect you automatically to the correct download page.

## 9. How to update patched apps?

To update a patched app, you need to patch and install the app again. 

Patch versions are completely different from the app version, and newer patches can exist even if the app version is the same as your currently patched app. See #3 in [Questions](questions.md).

## 10. Is Morphe affiliated with ReVanced?

Morphe is not affiliated with ReVanced. Morphe was created by a team of former ReVanced developers and contributors.

## 11. Capture logs 

1. (Only if the setting exists) Turn on `Miscellaneous > Debugging > Debug logging` in the settings (Ensure you have included the `Enable debugging` patch).  
2. Install the [Android developer tools](https://developer.android.com/tools/releases/platform-tools) on a computer, open a command prompt, and capture the logs using the command `adb logcat | grep 'morphe\|AndroidRuntime` to log both Morphe and crash logs. To save the logs to a file use  `adb logcat | grep 'morphe\|AndroidRuntime' > logs.txt`
3. Alternatively, you can use any Android app capable of [capturing logs](https://play.google.com/store/apps/details?id=com.dp.logcatapp) (to use these apps a one time setup is required using a computer and ADB).
4. Alternatively, in YouTube you can copy the most recent logs directly from the Debug settings menu (due to clipboard limitations the log is limited to the most recent log data). No ADB or computer setup is required. Crash logs can only be collected using ADB. 

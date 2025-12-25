# Frequently asked questions

Please read them before asking questions that have been asked too many times.

## 2 Is Morphe available on iOS or TV?

Morphe is a patcher for Android apps. Android is very different from iOS. Therefore, Morphe is not available on iOS. The nearest equivalent to Morphe on iOS is [Theos](https://theos.dev/). If your TV runs Android, it may be possible to use Morphe.

## 3 How to get Morphe?

Morphe is a patcher for Android apps. Getting Morphe means patching your app. To patch your apps, download Morphe Manager from [https://morphe.software](https://morphe.software) and Morphe CLI from [GitHub](https://github.com/MorpheApp/morphe-cli).

## 6 How can I help?

Since we are an open-source community and depend on outside help, you can always check out [our GitHub repositories](https://github.com/MorpheApp) and contribute to Morphe by creating an issue or pull request. If you are fluent in both English and another language, you can help imrpove the translations by visiting [https://translate.morphe.software](https://translate.morphe.software) and creating a Crowdin account.

And [financial donations](https://morphe.software/donate) are always welcomed.

## 7 Can I patch the latest YouTube (Can I patch newer than the recommended version)?

Morphe tries to support the very latest versions of YouTube. If you like exploring and are willing to accept that some unidentified bugs may exist, then you can try patching the latest YouTube with Morphe. If you don't like to tinker or repatch often, then always patch the version of YouTube recommended by Morphe.

Be aware that even if there are no unidentified bugs or issues with patching the latest YouTube, it will be full of [a/b tests](https://en.wikipedia.org/wiki/A/B_testing) that show up for some users as strange UI layouts and unreleased work in progress features.

If Morphe Manager fails to patch the latest YouTube, or you find patch bugs present in the latest YouTube but the bugs are _not_ present in the recommended YouTube, then please open an issue in the [GitHub patches](https://github.com/MorpheApp/morphe-patches) repo (Be sure to search for duplicate issues before creating a new issue).

## 9 Where to get (full) APKs

You can get (full) APKs from sites such as [APKMirror](https://www.apkmirror.com/) or [APKPure](https://apkpure.net/de). An APK ends with the extension `.apk`.

If only split apks are available (`apkm` or `xapk` files), then tools like [AntiSplit M](https://github.com/AbdurazaaqMohammed/AntiSplit-M) can convert `apkm`/`xapk` of your device architecture to regular `apk` for use with Morphe Manager.

## 10 Capture logs 

1. Turn on `Miscellaneous > Debugging > Debug logging` in the settings.
2. Install the [Android developer tools](https://developer.android.com/tools/releases/platform-tools) on a computer, open a command prompt, and capture the logs using the command `adb logcat | grep 'morphe\|AndroidRuntime` to log both Morphe and crash logs. To save the logs to a file use  `adb logcat | grep 'morphe\|AndroidRuntime' > logs.txt`
3. Alternatively, you can use any Android app capable of [capturing logs](https://play.google.com/store/apps/details?id=com.dp.logcatapp) (to use these apps a one time setup is required using a computer and ADB).
4. Alternatively, in YouTube you can copy the most recent logs directly from the Debug settings menu (No ADB or computer setup is required). But due to clipboard limitations the log is limited to the most recent log data.  Crash logs can only be collected using a computer and ADB.

## 12 Where to get microG?

If you don't have microG installed, then the app will automatically redirect you to the correct [download page](https://morphe.software/microg).

## 13 Is Morphe affiliated with ReVanced?

Morphe is not affiliated with ReVanced. Morphe was created by a team of former ReVanced developers and contributors.

## 14 How to update patched apps?

To update a patched app, you need to patch and install the app again. You do not need to uninstall your existing patched app to upgrade the patched app.

Patch versions are completely different from the app version, and newer patches can exist even if the app version is the same as your currently patched app. Check the `Settings > Morphe > About` screen to see if your patches are outdated.

## 15 How do I backup my YouTube Morphe settings?

Morphe personalized settings are handled using text copy paste.

Go to: `Settings > Morphe > Miscellaneous > Import / Export`

Press the copy button to copy your settings to the clipboard. Paste your settings somewhere safe to save (Note app, email message, etc).

To restore your settings, paste your settings into the same `Import / Export` Morphe menu and press `Import`.

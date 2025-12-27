# Frequently asked questions

## 1. What is Morphe?

Morphe is a patcher for Android apps. It can patch apps and add extra features and customization.

## 2. What apps can Morphe patch?

You can patch any app you want, as long as you want YouTube or YT Music. We're constantly working on expanding support to more apps.

## 3. How to get Morphe?

[Download Morphe](https://morphe.software/download) and follow the prompts to patch your app. Alternatively, you can follow the [Morphe CLI documentation](https://github.com/MorpheApp/morphe-cli/tree/main/docs) to use Morphe CLI to patch using a computer.

## 4. Is Morphe safe?

As safe as modifying obfuscated bytecode can be. All source code for Morphe is open-source and free for anyone to inspect. Our community actively reviews and contributes to the codebase.

## 5. Will Morphe brick my phone?

Only if your phone decides to brick itself. Otherwise your device will be fine. Morphe only modifies app packages and doesn't touch system files.

## 6. Can I customize apps to my preference?

Yes, but don't blame Morphe if your app becomes too customized for you to handle. It's recommended to customize up to your preference level and no more.

## 7. Is Morphe available on iOS or TV?

Morphe is a patcher for Android apps. Android is very different from iOS so it is not available on iOS. If your TV runs Android, it may be possible to use Morphe.

## 20. Can I patch the latest YouTube version? (Can I patch newer than the recommended version?)

Morphe tries to support the very latest versions of YouTube. If you like exploring and are willing to accept that some unidentified bugs may exist, then you can try patching the latest YouTube with Morphe. If you do not like to experiment with software or repatch often, then always patch the version of YouTube recommended by Morphe.

Be aware that even if there are no unidentified bugs or issues with patching the latest YouTube, it may be full of [a/b tests](https://en.wikipedia.org/wiki/A/B_testing) that show up for some users as strange UI layouts and unreleased YouTube work-in-progress features.

If Morphe Manager fails to patch the latest YouTube, or you find patch bugs present in the latest YouTube that are _not_ present in the recommended YouTube, then please open an issue in the [GitHub patches](https://github.com/MorpheApp/morphe-patches/issues?q=is%3Aissue) repo (Be sure to search for duplicate issues before creating a new issue).

## 21. What if I want to use an older version of YouTube?

Morphe supports patching some older versions of YouTube. At the present time the oldest versions that can be patched are:
- YouTube: `20.14.43`
- YT Music: `7.29.52`

But always ensure you have the latest patches, even when patching older app versions.

## 22. How to update patched apps?

To update a patched app, you need to patch and install the app again. You do not need to uninstall your existing patched app to upgrade the patched app.

Patch versions are completely different from the app version, and newer patches can exist even if the app version is the same as your currently patched app. Check the `Settings > Morphe > About` screen to see if your patches are outdated.

## 23. Where to get (full) APKs?

You can get (full) APKs from sites such as [APKMirror](https://www.apkmirror.com/) or [APKPure](https://apkpure.net/). An APK ends with the extension `.apk`.

If only split apks are available (`apkm` or `xapk` files), a tool like [AntiSplit M](https://github.com/AbdurazaaqMohammed/AntiSplit-M) can convert an `apkm`/`xapk` of your device architecture to a regular `apk` for use with Morphe Manager.

## 24. I found a random website that offers YouTube APK's patched with Morphe. Are those safe to use? 

What you found is a "pre-patched" apk patched by someone else.

Since there's no way to know if the APK was maliciously altered by someone else,
for the safety of your device and your online accounts **you should not use pre-patched APKs**.

The official and only safe way to use Morphe is to patch yourself on your phone using the [Android Morphe app](https://morphe.software) or on your computer using [Morphe CLI](https://github.com/MorpheApp/morphe-cli/tree/main/docs). 

## 30. Where to get microG GmsCore?

If microG is required for your patched app, you will be directed to the correct [microG download page](https://morphe.software/microg) upon opening the app.

## 32. How do I backup my YouTube Morphe settings?

Morphe uses a text configuration for personalized settings which can be copied and pasted.

Go to: `Settings > Morphe > Miscellaneous > Import / Export`

Press the copy button to copy your settings to the clipboard. Paste your settings somewhere safe to save them (Notes app, email message, etc).

To restore your settings, paste your settings into the same `Import / Export` textbox and press `Import`.

## 33. How can I make links open in a patched app?

> [!NOTE]
>  <details>
>  <summary><strong>Information for MIUI users:</strong></summary>
>  <br>
>
> If you are using MIUI, you may need to use the `Manage applications` settings within the [Hidden Settings for MIUI](https://play.google.com/store/apps/details?id=com.ceyhan.sets) app in order to follow the steps below. 
>
>  </details>

1. If the unpatched version of the app is installed, open its App info and disable `Set as default/Open by default > Open supported links`.
2. Open the App info of the patched app and enable `Set as default/Open by default > Open supported links`.
3. Return to the previous page and enable all of the Supported web addresses.

## 34. How do I use YT Music with Android Auto?

1. Go to the [Android Auto](https://developer.android.com/training/cars/testing?utm_source=android-studio-app#developer-mode) settings on your device.
2. Scroll down to `Version and permission info`.
3. Tap on it 10 times to enter developer mode.
4. Tap the 3 dots in the upper-right corner of your screen and open the Developer settings.
5. Scroll down and enable `Unknown sources`.

Be aware that most YT Music Android Auto features require a YouTube Premium subscription.

## 40. Capture logs 

1. Turn on `Miscellaneous > Debugging > Debug logging` in the settings.
2. Install the [Android developer tools](https://developer.android.com/tools/releases/platform-tools) on a computer, open a command prompt, and capture the logs using the command `adb logcat | grep 'morphe\|AndroidRuntime` to log both Morphe and crash logs. To save the logs to a file use  `adb logcat | grep 'morphe\|AndroidRuntime' > logs.txt`
3. Alternatively, you can use any Android app capable of [capturing logs](https://play.google.com/store/apps/details?id=com.dp.logcatapp) (to use these apps a one time setup is required using a computer and ADB).
4. Alternatively, in YouTube you can copy the most recent logs directly from the Debug settings menu (No ADB or computer setup is required). But due to clipboard limitations the log is limited to the most recent log data. Crash logs can only be collected using a computer and ADB.

## 50. How can I help?

Since we are an open-source community and depend on outside help, you can always check out [our GitHub repositories](https://github.com/MorpheApp) and contribute to Morphe by creating an issue or pull request.
You can also help with translations on [Crowdin](https://translate.morphe.software).

Additionally, [financial donations](https://morphe.software/donate) are always welcome.

## 51. Why the name Morphe?

Because "Android App Modification And Transformation Tool" (AAMATT) is not very catchy. And because Morphe implies it morphs your apps into something better.

## 52. Is Morphe affiliated with ReVanced?

Morphe is not affiliated with ReVanced. Morphe was created by a team of former ReVanced developers and contributors.

## 52. What is Morphe's privacy policy?

The [website](https://morphe.software) uses [Umami](https://umami.is) for analytics: no cookies, no personal data, nothing sold, and nothing shared. Morphe does not add analytics or data collection to any patched apps.

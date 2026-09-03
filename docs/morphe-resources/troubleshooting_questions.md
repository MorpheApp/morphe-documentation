# Troubleshooting and Frequently asked questions

## 4. YouTube Audio track menu is missing

Ensure `Settings > Morphe > About` says "You are using the latest patches"

Then change to `TV` in : `Settings > Morphe > Miscellaneous > Spoof video streams > Default client`

## 5. Videos play with auto-dubbed audio translations

Ensure `Settings > Morphe > Video > Force original audio language` is enabled.

You may also need to change to a spoof client that supports multiple audio tracks (see item 4 above).

If the audio is still auto-dubbed and "Stats for nerds" always shows `Android Studio`, then the original audio cannot be forced and currently there is no solution.

## 7. Stable volume is not available

Change the spoof client to either `visionOS` or `TV Simply`, see item 4 above.

## 8. Children/music videos do not play and an error is shown

A YouTube account is required to play most children's videos. Ensure you are logged into a YouTube account and incognito mode is not enabled.

## 15. App shows "No internet connection"

This issue can happen after making changes to your Google account. Uninstall and reinstall [microG](https://morphe.software/microg).

## 16. YouTube is showing the player overlay buttons all the time

Verify you did not enable the stock YouTube accessibility feature:
`Settings > Accessibility > Accessibility player > Off`

## 18. YouTube Watch history is not being saved

If you use a system ad-blocker, then whitelist `s.youtube.com`. Otherwise verify watch history works with unpatched YouTube, and check your YouTube/Google account permissions and ensure your account watch history is enabled.

## 20. YouTube Shorts tab button is missing

Disable `Settings > Morphe > General > Navigation buttons > Hide Shorts button`.

## 21. YouTube now looks different and I want the old UI

Enable: `Settings > Morphe > General > Spoof app version`

and optionally pick a spoof version:
`Settings > Morphe > General > Spoof app target`

If you still don't have the old UI, then you can try patching an older version of YouTube.

Morphe supports patching some older versions of YouTube. At the present time the oldest versions that can be patched are:
- YouTube: `20.21.37`
- YT Music: `9.15.51`
- Reddit: `2026.04.0`

But always ensure you have the latest patches, even when patching older app versions.

## 22. MicroG Google login does not work

Disable the setting `MicroG > Privacy > Authenticate with device registration`

Use a username/password to log in. Some devices may require temporarily turning off 2-factor authentication.
Certain managed accounts such as Google Workspace, or family managed accounts may not work.

Some devices may require temporarily enabling the "Appear on top" MicroG overlay permission for login to work.

Some devices may require using the "Huawei login" button, even if not using a Huawei device.

## 30. Installation is blocked due to conflicting with an existing installation

This implies that you must remove the previous installation to solve the conflict.

This error can be caused by 'hidden' apps (Samsung Secure Folder, Android Work Profile, Xiaomi Hidden Apps, etc). If the same app is already installed but set hidden, then it needs to be unhidden and uninstalled before the patched app can be installed.

Patching in root mount mode avoids the conflict entirely, because the patched APK is mounted over the stock app instead of installed, see [Root mount](https://github.com/MorpheApp/morphe-manager/blob/main/docs/installers.md#root-mount-in-detail).

## 32. YouTube push notifications do not work

If you recently uninstalled/reinstalled MicroG, and did not also uninstall/reinstall patched YouTube, then you may need to clear the YouTube app data for push notifications to work again.

## 33. Links don't open in a patched app

> [!NOTE]
>  <details>
>  <summary><strong>Information for MIUI users:</strong></summary>
>  <br>
>
> If you are using MIUI, you may need to use the `Manage applications` settings within the [Hidden Settings for MIUI](https://play.google.com/store/apps/details?id=com.ceyhan.sets) app in order to follow the steps below. 
>
>  </details>

1. If the unpatched version of the app is installed, open its App info and disable `Set as default/Open by default > Open supported links`.
2. Open the App info of the patched app and enable `Set as default/Open by default > Open supported links`, then enable all url links shown.

If you have related apps that also open the same weblinks (such as the "YT Create" app by YouTube), then you may need to disable links in those apps as well.

Some devices may require manually enabling "link verification" using a connected computer and ADB.

`set-app-links-user-selection --user 0 --package (package name) true (url link)`

Run this command for each of the open with link urls. For YouTube this is:
```
adb shell pm set-app-links-user-selection --user 0 --package app.morphe.android.youtube true youtu.be
adb shell pm set-app-links-user-selection --user 0 --package app.morphe.android.youtube true youtube.com
adb shell pm set-app-links-user-selection --user 0 --package app.morphe.android.youtube true m.youtube.com
adb shell pm set-app-links-user-selection --user 0 --package app.morphe.android.youtube true www.youtube.com
adb shell pm set-app-links-user-selection --user 0 --package app.morphe.android.youtube true studio.youtube.com
```

 https://developer.android.com/training/app-links/verify-applinks#:~:text=adb%20shell%20pm%20set%2Dapp%2Dlinks%20%2D%2Dpackage%20PACKAGE_NAME%200%20all

## 34. Patched app does not work with Android Auto

1. Go to the [Android Auto](https://developer.android.com/training/cars/testing?utm_source=android-studio-app#developer-mode) settings on your device.
2. Scroll down to `Version and permission info`.
3. Tap on it 10 times to enter developer mode.
4. Tap the 3 dots in the upper-right corner of your screen and open the Developer settings.
5. Scroll down and enable `Unknown sources`.

You may need to update/change to [Morphe MicroG](https://morphe.software/microg) if you are using an old MicroG release.

Be aware that most YT Music Android Auto features require a YouTube Premium subscription.

## 35. SponsorBlock does not work

This likely means that the SponsorBlock servers are having issues. You can check the server status [here](https://status.sponsor.ajay.app/) and try again later.

## 50. YouTube or YT Music playback does not work

First ensure you are using the latest patches. You may be using outdated patches even if the app version has not changed. 

To update a patched app, you need to patch and install the app again. You do not need to uninstall your existing patched app to upgrade the patched app.

Patch versions are completely different from the app version, and newer patches can exist even if the app version is the same as your currently patched app. Morphe Manager puts an `Update` badge on the app card when the patches it was built with are outdated. Check the `Settings > Morphe > About` screen inside the patched app to see the same thing from there.

See [Updating a patched app](https://github.com/MorpheApp/morphe-manager/blob/main/docs/updating-patched-apps.md) for the full walkthrough.

Search for existing issues [here](https://github.com/MorpheApp/morphe-patches/issues?q=is%3Aissue%20state%3Aopen) as all known issues will have an existing issue.

If videos on YouTube are pausing instantly when you press the play button, then you must disable Picture-in-picture due to an issue with your OS/YouTube.

## Frequently asked questions

## 100. What is Morphe?

Morphe is a patcher for Android apps. It can patch apps and add extra features and customization.

## 101. What apps can Morphe patch?

You can patch any app you want, as long as you want YouTube, YT Music, or Reddit. We're constantly working on expanding support to more apps.

## 102. How to get Morphe?

[Download Morphe](https://morphe.software) and follow the prompts to patch your app. Alternatively, you can follow the [Morphe Desktop documentation](https://github.com/MorpheApp/morphe-desktop/tree/main/docs) to use Morphe Desktop to patch using a computer.

## 103. Is Morphe safe?

As safe as modifying obfuscated bytecode can be. All source code for Morphe is open-source and free for anyone to inspect. Our community actively reviews and contributes to the codebase.

## 104. Will Morphe brick my phone?

Only if your phone decides to brick itself. Otherwise your device will be fine. Morphe only modifies app packages and doesn't touch system files.

## 105. Can I customize apps to my preference?

Yes, but don't blame Morphe if your app becomes too customized for you to handle. It's recommended to customize up to your preference level and no more.

## 106. Is Morphe available on iOS or TV?

Morphe is a patcher for Android apps. Android is very different from iOS so it is not available on iOS. If your TV runs Android, it may be possible to use Morphe.

## 107. Can I patch the latest versions of apps? (Can I patch newer than the recommended version?)

Morphe tries to support the very latest versions of YouTube and Reddit. If you like exploring and are willing to accept that some unidentified bugs may exist, then you can try patching the latest releases with Morphe. If you do not like to experiment with software or repatch often, then always patch the version recommended by Morphe.

Be aware that even if there are no unidentified bugs or issues with patching the latest, it may be full of [a/b tests](https://en.wikipedia.org/wiki/A/B_testing) that show up for some users as strange UI layouts and unreleased work-in-progress features.

If Morphe Manager fails to patch the latest version of YouTube or Reddit, or you find patch bugs present in the latest that are _not_ present in the recommended version, then please open an issue in the [GitHub patches](https://github.com/MorpheApp/morphe-patches/issues?q=is%3Aissue) repo (Be sure to search for duplicate issues before creating a new issue).

## 110. I found a random website that offers YouTube APK's patched with Morphe. Are those safe to use? 

What you found is a "pre-patched" APK patched by someone else.

Since there's no way to know if the APK was maliciously altered by someone else,
for the safety of your device and your online accounts **you should not use pre-patched APKs**.

The official and only safe way to use Morphe is to patch yourself on your phone using the [Android Morphe app](https://morphe.software) or on your computer using [Morphe Desktop](https://github.com/MorpheApp/morphe-desktop/tree/main/docs). 

## 111. How do I patch Morphe with root?

On a rooted device Morphe Manager asks how the app should be patched before patching starts, in a `Choose patch mode` dialog. Pick `Root mount mode`.

Note that in this mode you need to **install** the original APK after downloading it, because the patched APK is mounted over the stock app.

The matching installer entry is `Settings > System > Installer > Root mount`, and it only applies to apps that were patched in root mount mode. See [Root mount](https://github.com/MorpheApp/morphe-manager/blob/main/docs/installers.md#root-mount-in-detail) for the details, including why branding cannot be changed for mounted installs.

## 112. Where to get microG GmsCore?

If microG is required for your patched app, you will be directed to the correct [microG download page](https://morphe.software/microg) upon opening the app.

## 113. How do I backup my YouTube Morphe settings?

Morphe uses a text configuration for personalized settings which can be copied and pasted.

Go to: `Settings > Morphe > Miscellaneous > Import / Export`

Press the copy button to copy your settings to the clipboard. Paste your settings somewhere safe to save them (Notes app, email message, etc).

To restore your settings, paste your settings into the same `Import / Export` textbox and press `Import`.

This covers the settings inside the patched app. Morphe Manager's own settings, patch selections, and signing keystore are backed up separately, see [Backing up Morphe and your keystore](https://github.com/MorpheApp/morphe-manager/blob/main/docs/backup-and-keystore.md).

## 116. Capture logs 

### Using Morphe log collector website

1. If using YouTube or YT Music, turn on `Miscellaneous > Debugging > Debug logging`. Do not turn on stack trace or protocol logging unless you are instructed to. If YouTube fails to launch then skip this step.
2. Enable developer mode on your phone: https://developer.android.com/studio/debug/dev-options
3. Verify "USB debugging" is enabled in your device Settings > Developer menu
4. Connect your phone to a computer with a usb cable
5. Visit https://debug.morphe.software on your computer
6. Press "Connect device" button on the log website
7. Approve the developer prompt on your phone
8. Press "save" button on the website

If logs do not show on the website, unplug your phone and retry again from step 4 thru 8

### Using a computer, usb cable, and terminal console

<!-- For patches it's better to grep with "morphe:" but that doesn't capture Morphe Manager logs -->
1. Turn on `Miscellaneous > Debugging > Debug logging` in the settings.
2. Install the [Android developer tools](https://developer.android.com/tools/releases/platform-tools) on a computer, open a command prompt, and capture the logs using the command `adb logcat | grep 'morphe\|AndroidRuntime` to log both Morphe and crash logs. To save the logs to a file use  `adb logcat | grep 'morphe\|AndroidRuntime' > logs.txt`
3. Alternatively, you can use any Android app capable of [capturing logs](https://play.google.com/store/apps/details?id=com.dp.logcatapp) (to use these apps a one time setup is required using a computer and ADB).
4. Alternatively, in YouTube you can copy the most recent logs directly from the Debug settings menu (No ADB or computer setup is required). But due to clipboard limitations the log is limited to the most recent log data. Crash logs can only be collected using a computer and ADB.

For problems with patching itself rather than with a patched app, export the logs from `Settings > System > Debug` in Morphe Manager, or copy the patcher log straight off the patching screen in Expert mode. See [How patching works and how to tune it](https://github.com/MorpheApp/morphe-manager/blob/main/docs/patching-process.md#when-patching-fails).

## 117. How can I help?

Since we are an open-source community and depend on outside help, you can always check out [our GitHub repositories](https://github.com/MorpheApp) and contribute to Morphe by creating an issue or pull request.
You can also help with translations on [Crowdin](https://morphe.software/translate).

Additionally, [financial donations](https://morphe.software/donate) are always welcome.

## 118. Why the name Morphe?

Because "Android App Modification And Transformation Tool" (AAMATT) is not very catchy. And because Morphe implies it morphs your apps into something better.

## 119. Is Morphe affiliated with ReVanced?

Morphe is not affiliated with ReVanced. Morphe was created by a team of former ReVanced developers and contributors.

## 120. What is Morphe's privacy policy?

The [website](https://morphe.software) uses [Umami](https://umami.is) and Google Analytics 4: No cookies, no advertising, no profiling, and no data is sold or shared. Morphe does not add analytics or data collection to any patched apps.

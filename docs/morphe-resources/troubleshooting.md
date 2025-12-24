# Troubleshooting

This is a collection of common errors and fixes.

## 4 YouTube Audio track menu is missing

Change: `Settings > Morphe > Miscellaneous > Spoof video streams > Client` to `Android No SDK`

If the audio track menu is still not available or playback buffers at 1 minute, then currently there is no solution.

## 5 Videos play with auto-dubbed audio translations

Ensure `Settings > Morphe > Video > Force original audio language` is enabled.

You may also need to change to a spoof client that supports multiple audio tracks (see item 4 above).

If the audio is still auto-dubbed and "Stats for nerds" always shows `Android Studio`, then the original audio cannot be forced and currently there is no solution.

## 7 Stable volume is not available

Stable volume is not available when using most Spoof video streams.

## 8 Children/music videos do not play and an error is shown

A YouTube account is required to play most children's videos. Ensure you are logged into a YouTube account and incognito mode is not enabled.

## 15 App shows "No internet connection"

This issue can happen after making changes to your Google account. Uninstall then reinstall microG.

## 18 YouTube Watch history is not being saved

If you use a system ad-blocker, then whitelist `s.youtube.com`. Otherwise check your YouTube/Google account permissions and ensure your account watch history is enabled.

## 19 The first Short opened has a delay before playback starts

Showing Shorts dislikes requires fetching dislikes before the first Short starts playing. This limitation only applies to the first Short opened and does not occur when swiping to other Shorts.

The only way to remove this delay is to turn off `Settings > Morphe > Return YouTube Dislike > Show dislikes on Shorts`

## 20 YouTube Shorts tab button is missing

Disable `Settings > Morphe > General > Navigation buttons > Hide Shorts button`

## 21 Morphe Manager is crashing/not working

Morphe Manager is still a work in progress. Before submitting an issue, ensure it is not duplicating an existing issue.

## 22 Google login does not work

Use a username/password to log in. Some devices may require temporarily turning off 2 factor authentication.

## 23 Links don't open in a patched app

Follow [this](https://support.google.com/pixelphone/answer/6271667). The process may vary for your device. You may need to disable or uninstall the unpatched app that occupies the links to set them for the patched app.

## 30 Installation is blocked due to conflicting with an existing installation

This implies that you must remove the previous installation to solve the conflict.

This error can be caused by 'hidden' apps (Samsung Secure Folder, Android Work Profile, Xiaomi Hidden Apps, etc). If the same app is already installed but set hidden, then it needs to be unhidden and uninstalled before the patched app can be installed.

## 35 SponsorBlock does not work

The servers of SponsorBlock are likely having issues right now. Review the [current status](https://status.sponsor.ajay.app/) of SponsorBlock.

## 40 Patched app does not work with Android Auto

Enable [Android Auto developer mode](https://developer.android.com/training/cars/testing#developer-mode), then enable "Unknown sources" in the Android Auto developer menu.

## 50 YouTube or YouTube Music playback does not work

First ensure you are using the latest patches. You may be using outdated patches even if the app version has not changed. See [here](https://github.com/MorpheApp/morphe-documentation/blob/main/docs/morphe-resources/questions.md#14-how-to-update-patched-apps) for additional information on updating.

Search for existing issues [here](https://github.com/MorpheApp/morphe-patches/issues?q=is%3Aissue%20state%3Aopen) as all known issues will have an existing issue.

If videos on YouTube are instantly paused when you press the play button, then you must disable Picture in Picture due to an issue with your OS/YouTube.


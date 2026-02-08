# Troubleshooting

This is a collection of common errors and fixes.

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

## 19. The first Short opened has a delay before playback starts

Showing Shorts dislikes requires fetching dislikes before the first Short starts playing. This limitation only applies to the first Short opened and does not occur when swiping to other Shorts.

The only way to remove this delay is to disable `Settings > Morphe > Return YouTube Dislike > Show dislikes on Shorts`.

## 20. YouTube Shorts tab button is missing

Disable `Settings > Morphe > General > Navigation buttons > Hide Shorts button`.

## 21. YouTube now looks different and I want the old UI

Enable: `Settings > Morphe > General > Spoof app version`

and optionally pick a spoof version:
`Settings > Morphe > General > Spoof app target`

## 22. MicroG Google login does not work

Use a username/password to log in. Some devices may require temporarily turning off 2 factor authentication. Certain managed accounts such as Google Workspace may not work.

Some devices may require temporarily enabling the "Appear on top" MicroG overlay permission for login to work.

## 30. Installation is blocked due to conflicting with an existing installation

This implies that you must remove the previous installation to solve the conflict.

This error can be caused by 'hidden' apps (Samsung Secure Folder, Android Work Profile, Xiaomi Hidden Apps, etc). If the same app is already installed but set hidden, then it needs to be unhidden and uninstalled before the patched app can be installed.

## 32. YouTube push notifications do not work

If you recently uninstalled/reinstalled MicroG, and did not also uninstall/reinstall patched YouTube, then you may need to clear the YouTube app data for push notifications to work again.

## 33. Links don't open in a patched app

Follow [this](questions.md#33-how-can-i-make-links-open-in-a-patched-app).

## 34. Patched app does not work with Android Auto

See [here](questions.md#34-how-do-i-use-yt-music-with-android-auto)

## 35. SponsorBlock does not work

This likely means that the SponsorBlock servers are having issues. You can check the server status [here](https://status.sponsor.ajay.app/) and try again later.

## 50. YouTube or YT Music playback does not work

First ensure you are using the latest patches. You may be using outdated patches even if the app version has not changed. See [here](questions.md#11-how-to-update-patched-apps) for additional information on updating.

Search for existing issues [here](https://github.com/MorpheApp/morphe-patches/issues?q=is%3Aissue%20state%3Aopen) as all known issues will have an existing issue.

If videos on YouTube are pausing instantly when you press the play button, then you must disable Picture-in-picture due to an issue with your OS/YouTube.

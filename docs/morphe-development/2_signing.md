# 🔏 Signing your patches

Signing is optional. A signed patches file carries a signature that Morphe checks before it installs an update of your patches.

## ❓ What it does

- Morphe remembers the key of the first signed release it installs from your repository.
  From then on it only installs releases signed by that key.
- If a release is changed or swapped after you published it, for example by someone with access to your
  GitHub releases, Morphe refuses it and keeps the version that is installed.
- Morphe shows the key as a short fingerprint, such as `3931 c916 5ee4 266a`, in the details of your patch source.

Signing does not make patches safe. Anyone who can push to your repository can also publish a signed release
through your release workflow. Keep the access to your repository and its secrets safe.

## 🚀 Set up signing

The [patches template](https://github.com/MorpheApp/morphe-patches-template) is already set up for signing:

1. Run `./gradlew generateSigningKey` in your patches project.
   It creates `morphe-signing.pub` and `morphe-signing.key`.
2. Commit `morphe-signing.pub`. Never commit `morphe-signing.key`, the template ignores it.
3. Add the content of `morphe-signing.key` as the `MORPHE_SIGNING_KEY` secret in your repository
   (Settings > Secrets and variables > Actions).
4. Keep a backup of `morphe-signing.key` somewhere safe, like a password manager, and delete the file.

Every release is signed from then on, dev releases included. The release workflow also publishes your
public key in `patches-bundle.json`, so Morphe knows your key before it installs your first release.

If your repository was created from an older template, add `MORPHE_SIGNING_KEY: ${{ secrets.MORPHE_SIGNING_KEY }}`
to the `env` of the `Release` step in `release.yml`, and `"publicKeyPath": "morphe-signing.pub"` to the
`releaseJson` of `@MorpheApp/changelog` in `.releaserc`.

## 🔑 Losing or replacing a key

If the key is lost or leaked, create a new one the same way and replace the secret.
Morphe then refuses your next release until the user confirms the new key, so tell your users that you changed it.

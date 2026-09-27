# LifeRec GitHub Actions

The repository now includes a GitHub Actions workflow that builds a debug APK automatically on pushes and pull requests to `master`.

## APK artifact

Open **GitHub → Actions → Build LifeRec APK → workflow run → Artifacts** and download **LifeRec-debug-apk**.

## Security note

The original project contained hard-coded local signing credentials and an absolute developer-machine keystore path. Those values have been removed from `app/build.gradle`. CI currently produces an unsigned-by-custom-keystore **debug APK**, which is intended for testing.

For a production release, use a GitHub Actions secret-backed signing configuration rather than committing a keystore or password to source control.

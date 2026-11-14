# Bounce Lab

Bounce Lab is an original, offline-first mobile ragdoll physics playground for Android. It takes broad inspiration from Roblox physics sandboxes such as [Realistic Ragdoll Engine](https://www.roblox.com/games/81230874545623/Realistic-Ragdoll-Engine), while using original code, visuals, arenas, and progression.

## Play

- Choose Bounce Bay, Wind Tunnel, or Bump Course.
- Drag the ragdoll by a limb and release to throw it.
- Use Boost for a quick launch, Reset to start over, and Bank to save the run.
- Earn tokens, keep local high scores, and unlock character colors in the Locker.

Runs, scores, tokens, and unlocked colors are stored on the device. The game does not require an account or network connection while playing.

## Android APK

The GitHub Actions workflow builds a release APK from the Expo project and uploads it as a workflow artifact. After the workflow finishes, download `bounce-lab-android-apk` from its run summary.

### Run the GitHub Actions build

1. Extract this archive on your computer.
2. Create a GitHub repository and push the extracted project files to its `main` branch. Keep the `.github/workflows/android-apk.yml` file in place.
3. Open the repository's **Actions** tab. Select **Build Android APK**, then choose **Run workflow** if it has not already started from the push.
4. Open the completed run and download the `bounce-lab-android-apk` artifact.

The APK is built for release and the game works without a network connection after installation.

### Build locally

Requires Node.js 24, pnpm 10, Java 17, and the Android SDK:

```bash
pnpm install --frozen-lockfile
cd artifacts/mobile
pnpm exec expo prebuild --platform android --no-install
cd android
./gradlew assembleRelease
```

The APK is written to `artifacts/mobile/android/app/build/outputs/apk/release/app-release.apk`.

## Development

This project is part of the Replit pnpm workspace:

```bash
pnpm install --frozen-lockfile
pnpm --filter @workspace/mobile run typecheck
```

The current app is a 2D physics-based interpretation, not a copy of Roblox's game code or content.
# ragdoll-sandbox
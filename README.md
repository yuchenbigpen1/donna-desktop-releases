# Donna for Mac

This repository distributes the **Donna desktop app for macOS**. It holds release
artifacts only. There is no source code here, and none is planned: Donna's source
lives in a private repository.

Donna is at [meetdonna.xyz](https://meetdonna.xyz). The desktop app opens the same
Donna in its own window instead of a browser tab.

## Download

Builds are published on the [releases page](https://github.com/yuchenbigpen1/donna-desktop-releases/releases).

Each release carries:

| Asset | What it is |
| --- | --- |
| `Donna-arm64.dmg` | The installer. Open it and drag Donna to Applications. |
| `Donna-<version>-arm64.zip` | The same app, packaged for automatic updates. Not for manual download. |
| `latest-mac.yml` | The update manifest. Read by the app, not by you. |

**Requirements:** an Apple Silicon Mac (M1 or later) running macOS 11 Big Sur or
newer. Intel Macs are not supported yet.

## Updates

Donna updates itself. A running app notices a new release, downloads it quietly in
the background, and installs it the next time you quit and reopen. You never have
to come back here to stay current.

To check by hand, use **Donna → Check for Updates** in the menu bar.

## Verifying a build

Every release is signed with an Apple Developer ID certificate and notarized by
Apple, so macOS opens it without a security warning. To confirm that yourself
before installing, mount the disk image and run:

```
spctl -a -vvv -t exec /Volumes/Donna/Donna.app
```

Expect `accepted` and `source=Notarized Developer ID`. Anything else means the
file did not come from here intact.

## Reporting a problem

Open an [issue](https://github.com/yuchenbigpen1/donna-desktop-releases/issues) and
include the app version from **Donna → About Donna**, plus your macOS version.

## License

The software distributed here is proprietary. See [LICENSE](LICENSE).

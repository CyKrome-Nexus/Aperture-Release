# Aperture — Releases

Official distribution repository for **Aperture**, an enterprise-grade API workbench.

This repository hosts released binaries only. It contains no source code.

## Install

macOS and Linux can install from the terminal:

```bash
curl -fsSL https://github.com/CyKrome-Nexus/Aperture-Release/releases/latest/download/install.sh | bash
```

Platform-specific installers are also attached to every release:

```bash
curl -fsSL https://github.com/CyKrome-Nexus/Aperture-Release/releases/latest/download/install-mac.sh | bash
curl -fsSL https://github.com/CyKrome-Nexus/Aperture-Release/releases/latest/download/install-linux.sh | bash
```

The macOS installer extracts the `.app.tar.gz` into `/Applications` and removes
Gatekeeper quarantine attributes. The Linux installer installs the AppImage under
`~/.local/share/Aperture`, creates a desktop entry, and links `aperture` into
`~/.local/bin`.

## Download

Grab the latest build from the [**Releases**](../../releases/latest) page.

| Platform | File |
| --- | --- |
| macOS (Apple Silicon) | `Aperture_<version>_aarch64.dmg` or `Aperture_<version>_aarch64.app.tar.gz` |
| macOS (Intel) | `Aperture_<version>_x64.dmg` or `Aperture_<version>_x64.app.tar.gz` |
| Windows | `Aperture_<version>_x64_en-US.msi` or `Aperture_<version>_x64-setup.exe` |
| Linux | `Aperture_<version>_amd64.AppImage`, `Aperture_<version>_amd64.deb`, or `Aperture-<version>-1.x86_64.rpm` |

## Updates

Aperture updates itself. It checks this repository shortly after launch, and offers
the update in-app when there is one — download, install and restart are all handled
for you. You can also trigger a check from *Settings → About → Check for updates*.

Every update is cryptographically signed, and a build verifies that signature before
installing anything. An update that has been tampered with in transit is rejected.

In-app updating covers the macOS `.dmg`, the Windows installers and the Linux
`.AppImage`. The `.deb` and `.rpm` packages are owned by your system package manager,
so those installs do not self-update — grab a newer package when you want to move up.

`latest.json` on each release is the update feed. It is metadata, not a download.

## First launch

Builds are not code-signed or notarised yet, so macOS and Windows will show an
"unidentified developer" / SmartScreen warning on first launch. (This is separate
from update signing above, which is always on.)

- **macOS:** right-click the app → *Open* → *Open*.
- **Windows:** *More info* → *Run anyway*.
- **Linux (AppImage):** `chmod +x Aperture_*.AppImage && ./Aperture_*.AppImage`

Releases are published automatically by CI from the private source repository.

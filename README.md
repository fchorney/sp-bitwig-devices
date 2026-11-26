# SP Bitwig Devices

Native devices for Bitwig Studio, loaded with [Patchbay](https://github.com/shaboogen-dev/Patchbay)'s
**Framework: Nitro Devices**.

> **These devices need Patchbay**: an open-source (MIT) third-party mod loader for Bitwig, not made
> by Bitwig. Bitwig's own installation is never modified. Without Patchbay a device file does nothing.

## Devices

| Device | Type | What it does | Panel |
| --- | --- | --- | --- |
| [Sym EQ-5](Bitwig-6.1.7/Sym%20EQ-5.bwdevice) | Audio FX | EQ-5, then an FX chain, then the mirrored EQ-5 that undoes the EQ, so the effects work on the EQ'd signal and the EQ itself is cancelled. LUFS Learn on the output gain. | [Preview](previews/sym-eq-5.png) |

## Install

### Patchbay Launcher

Add this repository as a **Devices** source (`fchorney/sp-bitwig-devices`), refresh **Devices** and pick the
devices. The launcher chooses the build for your Bitwig version.

### Manually

1. Install a [Patchbay](https://github.com/shaboogen-dev/Patchbay/releases) release that supports your Bitwig
   version and follow `INSTALL.md` in its zip.
2. Download the folder for your Bitwig version:
   - `Bitwig-6.1.3-6.1.4/` for Bitwig 6.1.3 and 6.1.4
   - `Bitwig-6.1.7/` for Bitwig 6.1.7
3. Close Bitwig. In Patchbay, enable **Framework: Nitro Devices**, open **Tools → Device Folders** and add that
   folder (only one of the two: both builds share the same device ID). Click **Load**.
4. Find the device by name in Bitwig's device browser.

### Help texts

`*.help.properties` next to a device holds its help-view texts. They are shown by the
[Devices: Framework Device Help](https://github.com/fchorney/sp-bitwig-mods/tree/main/framework-device-help) mod
(manual installs: keep the file next to the device). Without the mod the device works normally and the help view
shows no texts.

### Projects that use a device you don't have

Bitwig crashes when it opens a project that uses one of these devices while the device isn't loaded (for example,
its folder was removed from Device Folders). The
[Devices: Missing Device Placeholder](https://github.com/fchorney/sp-bitwig-mods/releases/tag/bugfix-missing-device-placeholder-0.1.0-dev.1)
mod opens such a project with a pass-through **Missing Device** in the device's place instead. Saving the project
then replaces the device's settings, so add the device back and reopen without saving to keep them.

## Compatibility

| Device | 6.1.3 / 6.1.4 | 6.1.7 |
| --- | --- | --- |
| Sym EQ-5 | macOS 6.1.4: tested | macOS 6.1.7: tested |

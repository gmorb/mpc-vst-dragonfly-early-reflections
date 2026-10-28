![Dragonfly Early Reflections on MPC](https://raw.githubusercontent.com/gmorb/mpc-vst-dragonfly-early-reflections/main/docs/banners/early.png)

# Dragonfly Early Reflections for MPC OS

An unofficial port of the [Dragonfly Reverb](https://github.com/michaelwillis/dragonfly-reverb) **Early Reflections** plugin (3.2.10) by Michael Willis and Rob van den Berg, as a native insert effect for Akai MPC and Akai Force standalone devices, **Gen1** (32-bit: Force, MPC Live, Live II, One, X, Key 61) and **Gen2** (64-bit: MPC Live III, One G2, Key G2). A touchscreen page modelled on the original plugin's UI, Q-Link mapping, the original's presets, and full project recall.

Early reflections only: the first echoes of a space, without a reverb tail, for placing a sound in a room or as the first stage before another reverb. 8 reflection programs.

The DSP is upstream's own code, compiled with upstream's own flags, and null-tested against upstream's binary: see [Sound](https://github.com/gmorb/mpc-vst-dragonfly/blob/v1.3.0/docs/SOUND.md).

It shows up in MPC's plugin list as **Early Refl**, manufacturer **Dragonfly**.

This repo is the plugin's listing in the [MPC OS Plugin Catalog](https://sd88me.github.io/mpc-vst-plugins/). **The source code is in [gmorb/mpc-vst-dragonfly](https://github.com/gmorb/mpc-vst-dragonfly)**, which builds all four Dragonfly reverbs; each release here links to the exact source tag it was built from.

## Install

From the [MPC OS Plugin Catalog](https://sd88me.github.io/mpc-vst-plugins/) (its installers pick the right build for your device), or download from [Releases](../../releases/latest):

| Device | Download |
|---|---|
| Gen1 (32-bit): Force, MPC Live, Live II, One, X, Key 61 | `Early-Refl-<version>-mpc-armv7.zip` |
| Gen2 (64-bit): MPC Live III, One G2, Key G2 | `Early-Refl-<version>-mpc-aarch64.zip` |

Unzip, copy the folder to the device and run `install.sh` as root over SSH (modded firmware or SSH access required); the zip's `INSTALL.md` has the steps, and `uninstall.sh` removes it. The installer refuses the other generation's zip. Both builds have the same parameters and presets, so projects move between generations.

Using the Force VST plugins distribution (`vstscanner.sh`, Gen1)? Use the collection zip from [gmorb/mpc-vst-dragonfly](https://github.com/gmorb/mpc-vst-dragonfly/releases) instead. Use one install method per device: `vstscanner` rebuilds MPC's plugin list and drops plugins added by `install.sh`.

## Controls

| Control | Range | What it does |
|---|---|---|
| Dry Level | 0 to 100% | Level of the unprocessed signal |
| Wet Level | 0 to 100% | Level of the reflections |
| Program | Abrupt Echo, Backstage Pass, Concert Venue, Damaged Goods, Elevator Pitch, Floor Thirteen, Garage Band, Home Studio | Reflection pattern |
| Size | 10 to 60 m | Size of the simulated space |
| Width | 50 to 150% | Stereo width of the reverb |
| Low Cut | 0 to 200 Hz | Removes low frequencies from the reverb |
| High Cut | 1000 to 16000 Hz | Removes high frequencies from the reverb |

## Programs

8 reflection programs: Abrupt Echo, Backstage Pass, Concert Venue, Damaged Goods, Elevator Pitch, Floor Thirteen, Garage Band, Home Studio.

## Q-Links

Q-Link bank: **EARLY** (Dry Level, Wet Level, Size, Width, Low Cut, High Cut, Program).

## Tested

See [`tested.json`](tested.json): the devices and MPC OS versions each release was tested on.

## Source, credits and licence

- Source code, build, tests and changelog: [gmorb/mpc-vst-dragonfly](https://github.com/gmorb/mpc-vst-dragonfly) (each release here names its tag).
- Dragonfly Reverb by Michael Willis and Rob van den Berg; freeverb3 by Teru Kamogashira and others; Noto Sans by Google. Built with [mpc-vst-plugins](https://github.com/sd88me/mpc-vst-plugins).
- GPL-3.0-or-later ([LICENSE](LICENSE)), as Dragonfly Reverb. The release zips include the licence texts and the component notices.
- Not affiliated with or endorsed by the Dragonfly Reverb authors or by Akai Professional / inMusic.

Part of Dragonfly Reverb for MPC OS, with [Hall](https://github.com/gmorb/mpc-vst-dragonfly-hall), [Room](https://github.com/gmorb/mpc-vst-dragonfly-room), [Plate](https://github.com/gmorb/mpc-vst-dragonfly-plate) and [Early Reflections](https://github.com/gmorb/mpc-vst-dragonfly-early-reflections).

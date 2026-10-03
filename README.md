# Dragonfly Early Reflections for MPC OS

An unofficial port of the [Dragonfly Reverb](https://github.com/michaelwillis/dragonfly-reverb) Early Reflections plugin (3.2.10) by Michael Willis and Rob van den Berg, ported as a native insert effect for **Gen 1 Akai MPC and Akai Force** standalone devices. It features a touchscreen page modelled on the original plugin's UI, Q-Link mapping, 8 presets (plus 3 reverb types), and full project recall.

This plugin recreates the first reflections off walls, ceiling, and floor that occur within milliseconds of a direct sound—critical for convincing spatial depth without the washing tail of full reverb. Early reflections alone add realistic room size and intimacy to dry recordings.

![Dragonfly Early Reflections on MPC](https://raw.githubusercontent.com/gmorb/mpc-vst-dragonfly/main/docs/screenshots/early.png)

## What Are Early Reflections?

Early reflections are the first discrete echoes of sound reflecting off nearby surfaces—walls, ceiling, floor—before the dense, diffuse tail of reverb begins. They arrive within the first 50–100ms after the direct sound and are essential for conveying the size, shape, and character of a space. Unlike late reverb tails, early reflections preserve transient clarity while adding spatial cues that our brains interpret as room dimensions.

Early reflections are one of the most subtle yet powerful tools in mixing, especially suited for:

- **Acoustic instruments**: Adds realistic room character without washing out transients
- **Vocals**: Creates intimate, close-mic room ambience that preserves lyrical clarity
- **Drums**: Simulates the sound of drums in a small room, adding natural spatial cues
- **Piano and guitar**: Authenticates dry recordings with believable room reflections
- **Dialogue and post-production**: Matches recorded sources to the ambient space they'll be placed in
- **Electronic music**: Places synthetic elements in realistic spatial contexts

## Controls and Parameters

The Dragonfly Early Reflections interface mirrors the original desktop plugin with a fully functional touchscreen layout and Q-Link assignable parameters:

### Main Pages

- **Decay**: Controls the early reflection tail length from short (0.1s) to medium (0.5s). Adjust for tight rooms to slightly larger spaces.
- **Pre-Delay**: Sets the time before early reflections begin (0–50ms). Longer pre-delay preserves more transient definition; shorter values glue reflections tightly to the source.
- **Damping**: Low-pass filters early reflections, simulating sound absorption by soft surfaces. Higher damping creates warmer, more intimate reflections.
- **Diffusion**: Controls the density of early reflections. Lower values create distinct, discrete echoes; higher values produce smoother, more uniform spatial cues.
- **Width**: Adjusts the stereo width of early reflections from mono (centered) to wide (spread stereo field).
- **Mix**: Blends wet/dry signal from 0% (fully dry) to 100% (fully wet).

### Q-Link Assignments

All parameters can be mapped to the MPC's Q-Link knobs for real-time performance control. Default assignments include Decay, Damping, Pre-Delay, Width, and Mix—adjustable per preset via the Q-Link menu.

### Reverb Types

Three distinct early reflection tonal profiles are available, selectable from the preset menu:

1. **Type A (Small Room)**: Tight, intimate reflections with fast decay—ideal for vocal tracking and acoustic guitar
2. **Type B (Medium Room)**: Balanced reflections with moderate width and decay—versatile for drums and mixed sources
3. **Type C (Large Room)**: Extended reflections with wider stereo field—suited for ambient recordings and spatial experimentation

### Preset System

Eight user presets are provided, spanning:

- **Studio reflections**: Tight, dry, and controlled—perfect for close-mic vocals
- **Live reflections**: Natural room cues with moderate width—ideal for band recordings
- **Acoustic reflections**: Bright, present, with distinct early echoes—suited for guitar and piano
- **Ambient reflections**: Wider stereo field, smoother tails—great for atmospheric textures

Custom presets can be saved and recalled across sessions. Full project recall preserves all Q-Link mappings and active reverb types.

## Install

Two ways, from the same [Releases](../../releases). Use one per device (see [docs/CATALOG.md](docs/CATALOG.md)).

**From the [MPC OS Plugin Catalog](https://sd88me.github.io/mpc-vst-plugins/)**: download `<Name>-<version>-mpc-armv7.zip` with an `install.sh`; the zip's `INSTALL.md` has the steps.

**Force VST plugins distribution**: download `Dragonfly-Reverb-for-MPC-OS-<version>.zip`. It follows the Force VST plugins distribution layout ([docs/DISTRIBUTION.md](docs/DISTRIBUTION.md)): one self-contained folder per plugin.

Requires a Gen 1 Akai Force or MPC with SSH access (modded firmware such as MockbaMod) and the distribution's `Synths` folder with `vstscanner.sh`. The steps are written for the **Akai Force with MockbaMod**, which mounts its memory card at `/media/662522`:

1. Copy the `Dragonfly - VST - Early Reflections` folder into `/media/662522/Synths` (next to `vstscanner.sh`).
2. On the device: `sh /media/662522/Synths/vstscanner.sh` (afterwards just `vstscanner`). MPC restarts; the plugin is under VST, manufacturer "Dragonfly".

Other custom firmware (for example Hakai), or no `662522` card: put the folder in a `Synths` folder on any drive under `/media` (e.g. `/media/az01-internal/Synths`), find MPC's settings file (`find / -name MPC.settings`), and run `sh <that Synths folder>/vstscanner.sh <settings path>`. The release's README has the full steps, updating from 1.1.x, and troubleshooting.

## Screenshots

| Early Reflections |

![Dragonfly Early Reflections on MPC](https://raw.githubusercontent.com/gmorb/mpc-vst-dragonfly/main/docs/screenshots/early.png)

## Notes

This is an independent port maintained for the MPC OS community. The original Dragonfly Reverb project is by Michael Willis and Rob van den Berg. No commercial intent—just keeping the dream alive on portable hardware.

<p align="center">
  <img width="150" height="150" alt="aegis-icon" src="https://github.com/user-attachments/assets/5c49399c-06e2-4f57-a607-e48f72528b83" />
</p>

<h1 align="center">Aegis🛡️</h1>

<p align="center">
  A farming tool for RF Online.
</p>

## Overview

Aegis keeps repeatable combat routines in one focused tool. It supports multiple active clients, per-character profiles, controlled background input, live nearby-monster selection, and an optional MAU safeguard.

## Quick Start

1. Run `Aegis` and approve the Windows administrator prompt.
2. Logged in characters will automatically be detected.
3. Set the hunt range and, when available, select monster types from **Combat Control**.
4. Configure normal attacks, skill macros, loot, buffs, or MAU protection as needed.
5. Press **Start** on the client tab.

Use **Stop** before changing a running session's range or combat configuration.

## Features

### Combat Control
<img width="1835" height="839" alt="image" src="https://github.com/user-attachments/assets/be201ab8-14f1-4cb1-99d9-7f0192bb8440" />

- Automatic nearby-monster targeting with a configurable 100m to 1000m range.
- Multi-select monster list.
- Current manual target takes priority before automated targeting resumes.
- Normal attacks, skill macro hotkeys, and background loot input.
- Serialized input scheduling to avoid overlapping normal, macro, and loot messages.


https://github.com/user-attachments/assets/886fe1b1-a397-4968-a435-3fa52c8ac6bd

### Buff Sequence

The **Buff Cycle** is intended for buff macros that must be used between combat rotations. It temporarily pauses the active hunt so the game can finish the current attack animation before the configured buff keys are sent. Once the sequence is complete, Aegis waits for the chosen resume period and continues hunting automatically.

1. Enable **Buff Cycle** in **Attack Macros**.
2. Click a buff key field and press the in-game hotkey that contains the desired buff or buff macro. Use **+** to add another key; use **-** beside a row to remove it.
3. Set **Delay** to the spacing between buff key presses.
4. Set **Resume** to the time Aegis should wait after the last buff press before restarting combat. This gives longer cast animations time to complete.
5. Set **Every** to the buff duration in seconds. Aegis repeats the sequence after that interval while the hunt is running. Leave it at `0` to use **Cast Buffs** manually instead.

**Cast Buffs** immediately runs the configured sequence for the active client. During both manual and timed casts, normal attacks, skill macros, and loot input pause so they cannot collide with a buff key press. The hunt resumes automatically after the configured resume period.

### MAU Safeguard

- Works similarly to RF Sentinel, but improved.

- Optional HP threshold monitor for MAU characters.
- Cancels active combat, waits for the configured action-settle period, and sends the unmount command in the background.
- Safeguard follows the relevant combat session rather than affecting other active clients.



https://github.com/user-attachments/assets/26b2fad7-860c-43b0-a0b3-151989437215



### Automation

- Configurable skill macro hotkeys and repeat intervals.
- Buff cycles that pause hunting, cast configured hotkeys, then resume after the configured settle period.
- Per-character start and stop control for multi-client sessions.

### Live Information

- Optional live monster radar with hunt and current-target colors.
- Radar is disabled by default and can be enabled from **Settings** when needed.
- Nearby-monster selection remains available without rendering the radar.

### Profiles and Logs

- Save and load combat, macro, buff, range, loot, and safeguard preferences as named profiles.
- Profiles are stored in `aegis_profiles.json` beside the executable.
- Activity is written to the rolling `aegis_log.txt` file beside the executable.

## Files Created Beside the Executable

| File | Purpose |
| --- | --- |
| `aegis_profiles.json` | Saved profiles and character assignments. |
| `aegis_log.txt` | Rolling activity and status log. |

## Release Notes

### 2.0.1

- New Aegis visual identity and single-file native build.
- Compact combat-focused layout with scrollable supporting pages.
- Optional live radar and persistent profile storage beside the executable.
- Serialized background input and cleaned activity logs.


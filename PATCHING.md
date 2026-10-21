# Patching Kid Icarus DX

## Required original game

Use your own unmodified **Kid Icarus: Of Myths and Monsters (USA/Europe)** ROM.

| Property | Required value |
| --- | --- |
| File size | 262,144 bytes / 256 KiB |
| SHA-256 | `92c1fbf422abb8f09ca7fdbb563d1284108cc042e60e1222422986d9a59f9d97` |

IPS does not validate the input ROM for you. Check this fingerprint before patching; a different revision or an already patched ROM can produce a broken game.

On Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath 'your-original-game.gb'
```

## Install

1. Download `Kid-Icarus-DX-v0.91.ips` from the [preview release](https://github.com/pikamus/KidIcarusDX/releases/tag/v0.91).
2. In an IPS-compatible patcher, choose the original ROM and this patch.
3. Write the result to a new file, such as `Kid Icarus DX.gbc`.
4. Load that file in an emulator set to **Game Boy Color** mode.

The resulting ROM is **524,288 bytes / 512 KiB**. Its expected SHA-256 is in [release-manifest.json](release-manifest.json). The distributed patch's checksum is also listed in [patches/SHA256SUMS.txt](patches/SHA256SUMS.txt).

The release contains an IPS patch, not a playable ROM. GitHub's automatically generated source archives are repository snapshots; you can simply download the `.ips` asset instead.

## Saves and options

The patched cartridge uses **MBC1 with 8 KiB battery RAM**. Let the emulator create a save for this patched game; keep backups before trying any older saves. Original-game saves and emulator save states are not guaranteed to be interchangeable with this version.

Use the game's normal save/Continue system for progress. The title menu's **Save options** stores the four option switches separately. Unsaved option changes last only for the current session.

## Troubleshooting

- **Black screen or game will not start:** verify the input ROM hash, apply the patch once to a clean copy, and enable Game Boy Color mode.
- **Game starts without color:** check that you loaded the patched `.gbc` file and that the emulator is using CGB mode.
- **Colors differ from screenshots:** the screenshots use Modern – Accurate correction; emulator profiles and real screens display the same palette values differently.
- **NES music is unchanged:** turn on **NES stage music** in Options. Choose **Save options** if you want it enabled next time. Only the themes listed on the project page are replaced.
- **Options reset:** select **Save options** and press **A**, then close the emulator normally so its battery save is written.

For other issues, include your patch version, emulator/device and the stage or chamber where the problem occurs.

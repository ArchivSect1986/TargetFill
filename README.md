# 📀 TargetFill Pro

> ### 🎯 TargetFill is now built into [ArchivSector-OD](https://github.com/ArchivSect1986/ArchivSector-OD)
> Since **ArchivSector-OD v3.0**, everything TargetFill Pro does is also in its own **🎯 TargetFill** tab, alongside disc ripping, a "Make archival backup disc" button for finished rips, and one-click updates.
>
> This standalone script **stays available** for anyone who wants a small, no-install tool, and it still gets bug fixes. **New features go into ArchivSector-OD.** Folders made by either one work in the other.

Developed by **ArchivSect1986**, **TargetFill Pro** is a free Windows tool that fills an optical disc (or a USB drive) to **exactly 100% of its capacity**, so the data you're archiving sits in the safest part of the disc.

Right-click any folder, pick your disc size, and TargetFill works out exactly how much padding is needed. It splits that padding between the **start (lead-in)** and the **end (lead-out)** of the disc, which places your real data in the **middle tracks**, the area least affected by edge wear, handling, and aging. The padding is created with Windows **sparse files**, so even gigabytes of filler appear instantly and use no real disk space or SSD wear.

---

## 🚀 Key Features

* 🎯 **Exact-capacity filling:** Presets for **CD-R 700 MB, DVD-5, DVD-9, BD-25, BD-50, BD-100 and BD-128**, plus USB/SSD sizes from 16 GB to 2 TB and custom sizes. A safety margin is calculated automatically from the number of files.
* 🛡️ **Data centering:** Choose **Dual-Part Split** (filler at both the beginning and the end, with an adjustable balance) or put all filler at the **Start** or **End**. A live **radial track preview** shows where your data will land on the disc.
* ⚡ **Instant sparse fillers:** **Virtual (Sparse / Instant)** allocation uses the native Win32 sparse-file API, with no waiting and no wasted SSD writes. **Physical (Blocks)** mode writes real blocks when you need them.
* 💿 **ISO generation:** Build ready-to-burn `.iso` images directly with Windows' built-in IMAPI2, with a custom **disc volume label**. ImgBurn is detected automatically if you have it installed.
* 📚 **Auto-span multi-disc sets:** When a folder is too big for one disc (e.g. 12 GB onto 4.7 GB DVDs), TargetFill splits it into `Disc_01`, `Disc_02`… or straight into `YourFolder_DISC1.iso`, `_DISC2.iso`…, each padded to 100% and labeled "DISC 1 OF N".
* 🧹 **Clean Fillers:** Removes everything TargetFill generated in one click, leaving only your files.
* 🔄 **Built-in updater:** Checks GitHub for new versions when it opens (can be turned off) and installs updates safely. A broken download never replaces a working copy, and the previous version is backed up.

### 🧪 Expert Mode (Advanced Archival Options)

* 🔒 **SHA-256 archival manifest** of every file, optionally with the physical radial (mm) position of each range.
* ✅ **Standalone on-disc verifier:** a `Verify_Disc.bat` written to the disc that re-checks every file's SHA-256 years later, with nothing to install.
* 🩹 **PAR2 recovery files:** adds about 10% recovery data so damaged files can be repaired (requires `par2.exe`).
* 🗂️ **Searchable disc library:** each burn is logged to `_DiscCatalog.json` / `.csv`, an offline index of everything you've archived.
* 🗺️ **Detailed LBA sector map & report** of where everything sits on the disc.
* 🔎 **Pre-flight archival scanner:** warns about paths over 255 characters and filenames that aren't Joliet/UDF safe *before* you burn.
* 🖨️ **Printable artwork:** export a **disc label** and a **jewel case / inlay** graphic (`.png`).
* 🎲 **Random-data filler** (instead of zeros) and **stealth decoy names** (filler named like cache files) for special cases.
* 🔔 **Audio cues** when calculation or generation finishes.

---

## 🛠️ Requirements

* **Windows 10 or 11** with **Windows PowerShell 5.1** (built in).
* **Optional:** [ImgBurn](https://www.imgburn.com) for burning, and `par2.exe` for PAR2 recovery files.

---

## ⚙️ Installation & Usage

1. Download the latest release from the **Releases** page and unzip it.
2. Run **`Install.bat`** to add **TargetFill Pro** to the right-click menu for folders. (`Uninstall.bat` removes it.) You can also run **`Launch_TargetFill.bat`** directly.
3. **Right-click the folder** you want to archive and choose **TargetFill Pro**.
4. Pick your **target media**, a **placement mode**, and (optionally) a volume label, then click **Generate Split Filler** or, in Expert Mode, **Generate .ISO Image**.
5. Burn the folder or `.iso` with ImgBurn or Windows' disc burner.

Settings are saved in `%LOCALAPPDATA%\TargetFillPro\config.json`.

---

## ⚖️ Disclaimer

TargetFill Pro only creates filler files, manifests, and disc images from data you choose. It does not modify, copy-protect, or circumvent anything. It is distributed free under the MIT License "as-is", without warranty of any kind. Always verify important archives after burning.

---

**Also by ArchivSect1986:** [ArchivSector-OD](https://github.com/ArchivSect1986/ArchivSector-OD), an all-in-one optical disc archiving and game preservation control center, with TargetFill built in.

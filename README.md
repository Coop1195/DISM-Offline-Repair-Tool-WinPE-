# DISM Offline Repair Tool (WinPE)
**Author:** Coop1195

---

## 🛠 What It Does

This batch script automates the DISM offline repair process. It's designed for use in **Windows PE environments** to repair an offline Windows system using a Windows install disk as a source for system files.

---

## ✅ Features

- Prompts for required drive letters
- Mounts `install.wim` automatically
- Lets you select the appropriate Windows index
- Runs:
  - `DISM /RestoreHealth`
  - `SFC /scannow`
- Unmounts and discards WIM afterward
- Built-in error handling and pause prompts
- Supports `--version` argument

---

## 📦 Requirements

- Windows PE environment (bootable USB)
- USB stick with a Windows install ISO extracted
- `install.wim` file located in `\sources\` on that USB

---

## 💽 Drive Letter Usage

| Purpose                | Example | Notes                                     |
|------------------------|---------|-------------------------------------------|
| Offline Windows Drive  | `C:`    | This is your system drive (inaccessible Windows install) |
| Windows Install Media  | `F:`    | Must contain `sources\install.wim`        |
| Mount Workspace        | `G:`    | Temporary space to mount the image        |

Make sure the mount drive is not your USB or OS drive.

---

## 🧪 Usage

Boot into WinPE and run:

```cmd
DismRepairTool.bat

Or check the version:
DismRepairTool.bat --version

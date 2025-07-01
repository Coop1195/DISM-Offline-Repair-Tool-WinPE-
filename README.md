# DISM Offline Repair Tool (WinPE)

**Version:** 0.1.0  
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
- Another USB with a Windows Install Disk Image

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

1. Grab the latest Windows Edition ISO from Microsoft
2. Extract the ISO files to the root of a USB drive.
3. Image ISO file to another usb to create a Windows Install USB.
4. Copy the DismRepairTool program file to the root of the first usb drive with the extracted ISO files.
5. Eject your USBs, and boot into the Windows Install USB you made earlier. 
6. Insert Windows install USB
7. Boot into the Windows Install USB
8. Follow the prompts to get to the "Repair this PC"
9. Go through the menu options to find "Command Prompt". This is typically after the "Troubleshoot" option. 
10. Locate the drive with the extracted ISO files and the DISMRepairTool program
11. Run the script: .\DismRepairTool-V#.#.#

Or check the version:
DismRepairTool.bat --version
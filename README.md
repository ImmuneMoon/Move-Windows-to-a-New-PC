# 🚚 Move Windows to a New PC (Windows 10 & 11)

![Windows 10 | 11](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D4?logo=windows&logoColor=white)
![Covers: clone, drive move, clean install](https://img.shields.io/badge/Covers-clone%20%7C%20drive%20move%20%7C%20clean%20install-6f42c1)
![Requires administrator](https://img.shields.io/badge/Requires-Administrator-d73a49)
[![Last updated](https://img.shields.io/github/last-commit/ImmuneMoon/Move-Windows-to-a-New-PC?label=updated)](https://github.com/ImmuneMoon/Move-Windows-to-a-New-PC/commits/main)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey)](LICENSE)

**📄 [Download the PDF](Move-Windows-to-a-New-PC.pdf)**

## 📖 Overview
**Move Windows to a New PC** is a hub guide for every common way to move a Windows 10 or 11 install: cloning to a new drive in the same PC, moving your drive into a new PC or onto a new motherboard, starting fresh and bringing your files across, or setting up a new PC that already has Windows.

It starts with the two questions that decide everything: which route fits your situation, and whether your Windows license is allowed to move. Then it covers the steps every route shares, such as saving your BitLocker recovery key, the problems people hit on a new motherboard, and how to reactivate Windows afterward. Where another guide already covers a step in detail, this one links to it.

## ⚠️ Important Disclaimer
Moving a drive, changing BIOS storage settings, and converting a disk can leave a PC unable to start or lock you out of an encrypted drive. Back up anything you can't afford to lose, and save your BitLocker recovery key before you change any hardware. This guide isn't legal advice: the license terms for your copy of Windows decide whether it can move to a new PC, and they differ in some countries. For a home PC, Microsoft's supported way to put Windows on different hardware is a clean install, so if a moved drive gives you trouble, a clean install is the reliable fallback.

## 🚀 How to Use
Download the PDF above, or read on below. Start with **Section 1** to pick your route, then do **Sections 2 and 3** whichever route you choose. After that, jump to the section for your route, and finish with the checklist in **Section 9**. Moving your files onto new drives at the same time? **Section 10** covers copying whole data drives.

This guide works alongside:
* [Comprehensive Windows Migration and System Hardening Guide](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide) - Cloning Windows to a new SSD in the same PC, step by step.
* [Remove an Old Windows Install and Keep Your Files](https://github.com/ImmuneMoon/Remove-Old-Windows-Install-Keep-Your-Files) - A clean install on a new drive while your files stay on the old one.
* [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide) - Making the install USB, getting into the BIOS, installing, and activating.
* [DISM, SFC, and CHKDSK Windows Repair Guide](https://github.com/ImmuneMoon/DISM-SFC-CHKDSK-Windows-Repair-Guide) - Repairing Windows if anything acts up after the move.
* [Windows 10 Community Support Guide](https://github.com/ImmuneMoon/Windows-10-Community-Support-Guide) - Your options if you're staying on Windows 10.
* [IT Support Careers and Certifications](https://github.com/ImmuneMoon/IT-Support-Careers-and-Certifications#112-practice-with-this-sites-guides) - Moving Windows between PCs is good hands-on practice for CompTIA A+.

---

<!-- guide:start -->

## Contents

1. [Pick Your Route](#1-pick-your-route)
2. [Check Your License First](#2-check-your-license-first)
3. [Before You Move (Every Route)](#3-before-you-move-every-route)
4. [Route B: Move Your Drive to a New PC](#4-route-b-move-your-drive-to-a-new-pc)
5. [Reactivate Windows](#5-reactivate-windows)
6. [Routes C and D: Start Fresh and Bring Your Things](#6-routes-c-and-d-start-fresh-and-bring-your-things)
7. [Route A: Same PC, New Drive](#7-route-a-same-pc-new-drive)
8. [Other Methods](#8-other-methods)
9. [After the Move](#9-after-the-move)
10. [Copy Your Data Drives to New Drives](#10-copy-your-data-drives-to-new-drives)
11. [Troubleshooting](#11-troubleshooting)
12. [Sources](#12-sources)

---

## 1. Pick Your Route

| Your situation | Route | What happens | Go to |
|---|---|---|---|
| **Same PC, new drive** (for example, a hard drive to an SSD) | **A. Clone** | Copy your whole Windows drive onto the new one. Nothing to reinstall, and Windows normally stays activated because the motherboard is the same. | Section 7 |
| **New PC or new motherboard, and you want to keep your install** | **B. Move the drive** | Put your old drive (or a clone of it) in the new PC, fix the BIOS settings, install new drivers, and reactivate. | Sections 4 and 5 |
| **New PC, and you want a fresh start** | **C. Clean install** | Install Windows fresh, then bring your files, settings, and apps across. | Section 6 |
| **New PC that already has Windows on it** | **D. Files and apps only** | Keep the new PC's Windows and license, and copy your files and apps over. | Section 6 |

**A clean install (Route C or D) is the better call when:**
* **You're switching between AMD and Intel.** Your old install is full of drivers and tools for the old platform. It may well boot, but the leftovers can cause odd problems for months.
* **Your old install is old and cluttered,** or it has problems you've been putting up with.
* **The new PC came with its own Windows license.** Use it, and keep your old license where it belongs (see **Section 2**).
* **Your license can't move.** A license that came with your old PC stays with that PC.

Moving a drive to a new PC usually works, but Microsoft only supports moving Windows to different hardware after preparing it with Sysprep (**Section 8**), which isn't meant for a home PC. If Route B gives you trouble, a clean install is the supported way out.

## 2. Check Your License First
Whether your Windows can come with you depends on how you got it. Check this before you buy anything or take anything apart.

### 2.1 See how Windows is activated
1. Open the **Activation** page:
   * **Windows 11:** **Settings** > **System** > **Activation**, then expand **Activation state**.
   * **Windows 10:** **Settings** > **Update & Security** > **Activation**.
2. Read the message:

   | Message | What it means |
   |---|---|
   | **Windows is activated with a digital license linked to your Microsoft account** | The best case. After a hardware change, you can reactivate by signing in (**Section 5**). |
   | **Windows is activated with a digital license** | Activated, but the license isn't linked to a Microsoft account yet. Link it before you move (**Section 3**). |
   | **Windows is activated** | Activated, with no Microsoft account linked. If you entered a product key, keep it handy. |
   | **Windows is not activated** | Fix this on the old PC first, or plan to buy a license. |

### 2.2 Find your license channel
The channel tells you what kind of license you have.

1. Press `Windows Key + R`, type this, and press **Enter**:
   ```cmd
   slmgr.vbs /dli
   ```
   Type the `.vbs` part. If you type only `slmgr /dli`, the Run box can open a folder called `C:\Windows\System32\slmgr` instead. That folder is normal: it holds the tool's language files, such as `0409\slmgr.ini`.
2. Or run it in a terminal, which prints the result in the window:
   ```cmd
   cscript //nologo %windir%\System32\slmgr.vbs /dli
   ```
3. Look at the **Description** line, for example `Windows(R) Operating System, RETAIL channel`:
   * **RETAIL:** you bought Windows on its own, or upgraded from a copy you bought on its own.
   * **OEM** (such as `OEM_DM`, or names starting `OEM_COA` or `OEM_SLP`): Windows came with a PC, or a system builder key was used.
   * **VOLUME:** a work or school license.

For more detail, run the same command with `/dlv` instead of `/dli`. Neither needs an administrator window.

### 2.3 Can your license move?

| License | Can it move to a new PC? |
|---|---|
| **Retail** (boxed, downloaded, or bought from the Microsoft Store) | **Yes.** You can move it to another device that belongs to you, but only one device at a time: every time you move it, you must remove it from the old PC. |
| **Came with a PC** (OEM, preinstalled on a prebuilt or laptop) | **No.** It stays with that PC. It can only pass to someone else along with the PC itself. |
| **OEM System Builder keys, and cheap keys from key-selling sites** | These are meant for the first PC they're installed on. They may or may not reactivate on a new motherboard, so be ready to buy a license. |
| **Digital license from a free upgrade** (for example, Windows 7 or 8.1 to Windows 10, or 10 to 11) | It follows the license you upgraded from. Upgraded from a retail copy: it can move. Upgraded from Windows that came with the PC: it stays with that PC. |
| **Volume, work, or school** | It's covered by your organization's agreement, not the normal license terms. Ask your IT department. |

> **Outside the US:** Microsoft's transfer rules don't apply in Germany and some other countries, where local law decides instead. Microsoft lists them at [aka.ms/transfer](https://aka.ms/transfer).

## 3. Before You Move (Every Route)
Do these on the old PC while it still works.

1. **Link your Microsoft account to your license.** Go to **Settings** > **Accounts** > **Your info** and check that your Microsoft account email is shown above **Administrator**. Then open the **Activation** page. If it doesn't say **linked to your Microsoft account**, click **Add an account** and sign in.
2. **Note your edition.** Go to **Settings** > **System** > **About** and look for **Edition** under **Windows specifications**. The new install must be the same edition, usually **Home** or **Pro**, or it won't activate with your license.
3. **Find your product key,** if you have one. Look in the confirmation email from where you bought it, on a label inside the box, on a Certificate of Authenticity sticker, or in your Microsoft account's order history if you bought it from the Microsoft Store.
4. **Check for BitLocker and device encryption.** This matters most, because a new motherboard means a new TPM, and Windows will lock the drive until you enter the recovery key.
   * **Pro editions:** open Start, search for **Manage BitLocker**, and open it. Each drive shows **On**, **Off**, or **Suspended**.
   * **Windows 11:** **Settings** > **Privacy & security** > **Device encryption**.
   * **Windows 10:** **Settings** > **Update & Security** > **Device encryption**.
   * **If it's on:** in **Manage BitLocker**, click **Back up your recovery key** and save a copy somewhere other than this PC. Then, from another device, sign in at [aka.ms/myrecoverykey](https://aka.ms/myrecoverykey) and make sure the key is listed for this PC.
   * **If it's off:** there's nothing to save. Leave it off until the move is finished. Windows 11 can turn device encryption on by itself on new hardware, so check again after the first boot (**4.5**).

   If you're moving the drive (Route B), you can also suspend protection so the new PC doesn't ask for the key on first boot. In an administrator Command Prompt:
   ```cmd
   manage-bde -protectors -disable C: -rebootcount 0
   ```
   The `0` keeps it suspended until you resume it. While it's suspended, anyone with the drive can read it, so resume it straight after the move (**Section 9**).
5. **Back up your files** to an external drive or cloud storage, even if you plan to move the drive as it is.
6. **Write down your drive letters.** Open **File Explorer** > **This PC** and note what each letter holds, for example `D:` for games and `E:` for photos. Letters can change on a new PC, and apps such as game launchers look for their folders by letter.

   Note each drive's serial number too, and label the drives before you pull them. Two drives of the same model look identical, and the serial number on the label is the only way to tell them apart. In PowerShell:
   ```powershell
   Get-PhysicalDisk | Select-Object FriendlyName, SerialNumber, Size
   ```
7. **Save app settings and sign out of licensed apps.**
   * Turn on your browser's sync, or export your passwords to a password manager.
   * Note where your game launchers keep their libraries.
   * Collect license keys for paid software.
   * Some apps limit how many devices you can use, or tie activation to your hardware. Adobe apps and some games work this way, so sign out of them or deactivate them on the old PC first.
   * Save a list of your apps with winget, replacing `D:` with your USB stick's letter. Apps winget can't match get a warning, so note those by hand.
     ```cmd
     winget export -o D:\apps.json
     ```
8. **Download network drivers for the new PC.** If you're moving the drive to a new motherboard, put its chipset, LAN, and Wi-Fi drivers on a USB stick, from the board or PC maker's support page. Windows may not have a working network driver on the first boot. While you're there, get the board's newest BIOS file (**4.7**), and the new graphics driver if you're changing graphics card brands.
9. **Shut down fully** before you take the drive out. This command shuts down without the fast startup hibernation file, so Windows starts fresh on the new hardware:
   ```cmd
   shutdown /s /t 0
   ```

## 4. Route B: Move Your Drive to a New PC

### 4.1 Check how your old install starts
Do this on the old PC before you move anything.

1. Press `Windows Key + R`, type `msinfo32`, and press **Enter**. Look at **BIOS Mode**: it says **UEFI** or **Legacy**.
2. Check the drive's partition style. In PowerShell, run `Get-Disk` and look at the **Partition Style** column, or open **Disk Management**, right-click the disk, and choose **Properties** > **Volumes**.
   * **UEFI and GPT:** you're ready. This is what Windows 11 needs.
   * **Legacy and MBR:** the new PC may not start it, and Windows 11 needs UEFI. Convert the drive first with MBR2GPT, which changes it to GPT without deleting anything.

**Converting with MBR2GPT** (only for a Legacy and MBR install):
1. Suspend BitLocker if it's on (see **Section 3**). MBR2GPT stops if a volume is encrypted.
2. Open an administrator Command Prompt and check the drive first. It needs no more than three primary partitions and no extended partitions:
   ```cmd
   mbr2gpt /validate /allowFullOS
   ```
3. If it reports **Validation completed successfully**, convert it. This can't be undone:
   ```cmd
   mbr2gpt /convert /allowFullOS
   ```
4. The drive now only starts in UEFI mode, so switch the PC's firmware from Legacy (or CSM) to UEFI.

### 4.2 Move the drive
1. Shut down, switch off the power supply, and unplug the PC.
2. Move the drive to the new PC, into an M.2 slot or onto a SATA port and power cable.
3. If the new PC already has a drive with Windows on it, unplug that drive for the first boot, so the PC can't start the wrong Windows by mistake.

### 4.3 Set up the new PC's BIOS
The [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide#getting-into-your-bios) shows how to get into the BIOS. Look for these settings:

| Setting | What to choose |
|---|---|
| **Boot mode** (UEFI, CSM, or Legacy) | **UEFI**, with CSM turned off, for a GPT drive. CSM or Legacy only works for an MBR install, and only for Windows 10. |
| **Secure Boot** | **Enabled.** Windows 11 needs a PC that's capable of Secure Boot, and Microsoft recommends turning it on. It only works in UEFI mode. |
| **TPM** | **Enabled.** It may be called **AMD fTPM**, **Intel PTT**, **Intel Platform Trust Technology**, **Security Device Support**, or **TPM State**. Windows 11 needs TPM 2.0. |
| **Storage mode** (SATA mode, Intel VMD, RST, RAID) | Match the old PC if you can. On most desktops that's **AHCI**, with **Intel VMD** turned off. See **4.4**. |
| **Boot order** | Put your moved drive's **Windows Boot Manager** first. |

### 4.4 Storage mode and INACCESSIBLE_BOOT_DEVICE
Windows only loads the storage driver it was using on the old PC. If the new PC's storage controller runs in a different mode, Windows can't read its own drive and stops with a blue screen that says **INACCESSIBLE_BOOT_DEVICE**. Microsoft lists changing the storage controller mode in the BIOS, and moving the disk to a PC with a different controller, as causes.

Try these in order:

1. **Match the mode.** Set the new PC to **AHCI** and turn off **Intel VMD** or **RST/RAID**, if the BIOS allows it. Some Intel laptops and prebuilts come with VMD turned on.
2. **If you need RAID or VMD,** do a clean install with that mode already set (Route C). Intel says the storage mode must be set before Windows is installed, and that a system may not boot if it's changed afterward.
3. **Switching an install between AHCI and RAID** can sometimes be done by starting Windows once in Safe Mode, which loads the driver for the new mode. Dell documents a version of this method for its PCs. It needs a PC that still starts Windows, so do it on the old PC with the old setting, or on the new PC in a mode that boots:
   1. Suspend BitLocker first, if it's on.
   2. Press `Windows Key + R`, type `msconfig`, and press **Enter**. On the **Boot** tab, tick **Safe boot** with **Minimal** selected, and click **OK**. Or run this in an administrator Command Prompt:
      ```cmd
      bcdedit /set {current} safeboot minimal
      ```
   3. Restart into the BIOS, change the storage mode, and save.
   4. Windows starts in Safe Mode. Untick **Safe boot** in `msconfig`, or run:
      ```cmd
      bcdedit /deletevalue {current} safeboot
      ```
   5. Restart normally.

   This isn't guaranteed, and Intel's guidance is to set the mode before Windows is installed. If it doesn't work, use a clean install.

### 4.5 First boot and drivers
1. Start the PC and give Windows a few minutes. It finds the new hardware and may restart once or twice.
2. **Check the clock.** If the time or date is wrong, the **Windows Time** service may be stopped, so nothing corrects the new board's clock. A wrong clock throws off file dates and can break website sign-ins. In an administrator PowerShell window:
   ```powershell
   Set-Service W32Time -StartupType Automatic
   Start-Service W32Time
   w32tm /resync /force
   ```
3. Install the new board's **chipset** driver first, from the board maker's support page or from AMD or Intel. Then install the **LAN** and **Wi-Fi** drivers from your USB stick if the network isn't working.
4. Install the **graphics** driver from NVIDIA, AMD, or Intel.
5. Run **Windows Update** until nothing new appears.
6. Uninstall the old PC's extras in **Settings** > **Apps** > **Installed apps**: the old board's utilities, RGB lighting and fan control software, and any tools from the old PC's maker. They're written for hardware you no longer have.
7. **Check encryption.** Windows 11 can turn on device encryption by itself on new hardware, even if it was off on the old PC. In an administrator terminal, run:
   ```cmd
   manage-bde -status
   ```
   If a drive shows **Protection On**, or encryption in progress, either keep it and save the recovery key (check that it's listed at [aka.ms/myrecoverykey](https://aka.ms/myrecoverykey) with the same key ID), or turn it off:
   1. Turn it off in **Manage BitLocker** (Pro) or **Settings** > **Privacy & security** > **Device encryption**. Do data drives first, because they unlock with a key stored on the Windows drive.
   2. To stop Windows turning it back on, set the switch Microsoft documents for this, in an administrator Command Prompt:
      ```cmd
      reg add HKLM\SYSTEM\CurrentControlSet\Control\BitLocker ^
        /v PreventDeviceEncryption /t REG_DWORD /d 1 /f
      ```
   Decrypting runs in the background, and you can keep using the PC.
8. **Optional: clear out ghost devices.** In **Device Manager**, choose **View** > **Show hidden devices**. Grayed-out entries are devices that are no longer connected. They're normally harmless, so only uninstall one if you know it belonged to the old PC and it's causing a problem.

**Switching graphics card brands, such as NVIDIA to AMD?** Until the new driver is installed, Windows runs the card with **Microsoft Basic Display Adapter**, which drives only one monitor. A second screen staying black at this point doesn't mean the card or the port is faulty. Check **Device Manager** > **Display adapters**: if the card is listed and working, install its driver. Plug monitors into the graphics card, not the motherboard, because some boards' USB-C ports carry data only, with no video. To clear out the old brand's drivers and apps, run [Display Driver Uninstaller (DDU)](https://www.wagnardsoft.com/display-driver-uninstaller-ddu-) in Safe Mode, following its instructions.

**Switching between AMD and Intel?** If the old PC still runs, uninstall its chipset software (AMD's chipset software, or Intel's chipset, Management Engine, and RST software) before you move the drive. On the new PC, install the new platform's chipset driver before anything else. If the install still misbehaves, a clean install is the better fix.

### 4.6 Fix your drive letters
Your data drives may come up with different letters. Fix them before you open apps that use those drives, such as game launchers and OneDrive, or they may not find their folders.

Windows remembers a letter by the disk itself, not by the port it's plugged into, so a drive you moved normally keeps its letter. New drives, and drives whose letter is already taken, get the next free letter.

1. Right-click **Start** and choose **Disk Management**.
2. Right-click the volume with the wrong letter and choose **Change Drive Letter and Paths**.
3. Click **Change**, choose **Assign the following drive letter**, pick the letter from your notes, and click **OK**.
4. Click **Yes** at the warning.

Or, in an administrator PowerShell window, replacing the letters with yours:
```powershell
Set-Partition -DriveLetter W -NewDriveLetter E
```

Don't change the letter of the drive Windows is on. If a letter you need is taken, move the other drive to a spare letter first, or unplug the old drive that's using it.

### 4.7 Update the BIOS
A new board often ships with an older BIOS, and updates fix memory, stability, and security problems.

1. **Suspend BitLocker first** if any drive is encrypted. A firmware update changes what the TPM checks at startup, so without this, Windows asks for the 48-digit recovery key. In an administrator Command Prompt:
   ```cmd
   manage-bde -protectors -disable C: -rebootcount 1
   ```
   Protection comes back by itself after the next restart.
2. Download the newest BIOS from the board maker's support page, copy it to a FAT32 USB stick, and flash it with the board's built-in tool, such as **Q-Flash**, **EZ Flash**, **M-Flash**, or **Instant Flash**. Don't switch off the PC while it's flashing.
3. **Set your BIOS options again.** An update usually resets them: turn the memory profile (**EXPO** or **XMP**) back on, and check the boot order, **TPM**, and **Secure Boot**.
4. **Windows may ask you to set up your PIN again.** On many boards, a BIOS update resets the firmware TPM, where Windows Hello keeps its keys. Set the PIN up again. Nothing else is lost.
5. Some boards have a BIOS option that offers to install the maker's apps in Windows, and an update can turn it back on. Decline the install prompt, or turn the option off in the BIOS.

## 5. Reactivate Windows
After a big hardware change, such as a new motherboard, Windows may not find a matching license. Activation also checks that your copy isn't being used on more devices than its license allows.

1. **Connect to the internet and wait a little.** Then check the **Activation** page. A license that can move often activates by itself.
2. **Use the Activation troubleshooter.** Sign in as an administrator, then:
   1. **Windows 11:** **Settings** > **System** > **Activation** > **Troubleshoot**. **Windows 10:** **Settings** > **Update & Security** > **Activation** > **Troubleshoot**. The **Troubleshoot** option only appears when Windows isn't activated.
   2. Click **I changed hardware on this device recently**, then **Next**.
   3. Sign in with the Microsoft account linked to your license.
   4. Tick **This is the device I'm using right now** next to this PC, and click **Activate**.

   If your PC isn't in the list, check that you signed in with the same account that's linked to the license. If it says it can't reactivate Windows from these devices, go to step 4.
3. **Or enter your product key.** On the **Activation** page, click **Change product key** and enter it.
4. **If a retail key says it's already in use** (error **0xC004C008**), and you've removed it from the old PC, activate through Microsoft's activation portal or by phone. This often works when the troubleshooter and the key both fail.
   1. On the **Activation** page, click **Activate using the Product Activation Portal** if it's offered. Otherwise, press `Windows Key + R`, type `slui 4`, and press **Enter**.
   2. Windows shows an **Installation ID**. Enter it on Microsoft's portal, or read it out on the phone.
   3. You get a **Confirmation ID** back. Type it into Windows and click **Activate**.

   Phone activation isn't available for Windows 11 Pro Education or Pro for Workstations. To confirm it worked, run `slmgr.vbs /dli` and look for **License Status: Licensed**.
5. **If nothing works,** the license probably can't move, such as one that came with your old PC. Click **Go to Store** on the **Activation** page to buy one.

Remember that the edition must match. A Pro license won't activate Home, and a Home license won't activate Pro.

## 6. Routes C and D: Start Fresh and Bring Your Things

### 6.1 Route C: install Windows fresh
1. Make the install USB and install Windows with the [Windows Install Guide](https://github.com/ImmuneMoon/Windows-Install-Guide#installing-windows). If you're installing to a new drive and keeping your files on the old one, follow [Remove an Old Windows Install and Keep Your Files](https://github.com/ImmuneMoon/Remove-Old-Windows-Install-Keep-Your-Files#step-1-install-windows-with-the-old-drive-unplugged) too.
2. **Unplug your data drives** while you install, so only the target drive is connected. Setup then can't put its boot files on another drive, and you can't wipe the wrong one by mistake.
3. When it asks for a product key, click **I don't have a product key** if you're relying on a digital license, or enter your key.
4. Choose the edition your license covers, **Home** or **Pro**.
5. Once Windows is set up, activate it. If you moved a license from your old PC, use **Section 5**.

### 6.2 Bring your files and settings across
This applies to Route C and to Route D, a new PC that came with Windows.

**Windows Backup** (built into Windows 11 and Windows 10):
1. On the old PC, open the **Windows Backup** app and sign in with a personal Microsoft account. Work or school accounts don't work.
2. Choose what to back up: your **Desktop**, **Documents**, **Pictures**, **Videos**, and **Music** folders go to OneDrive, along with a list of your apps and settings such as Wi-Fi passwords and personalization.
3. On the new PC, sign in with the same Microsoft account during setup. Windows finds your backup and offers to restore it.
4. Your apps come back as pins on the Start menu. Microsoft Store apps reinstall from their pins, and other apps send you to their download page.

Free Microsoft accounts include 5 GB of OneDrive storage, so large folders need more storage or a copy by hand. Microsoft Edge has its own sync for browser settings. Windows 11 briefly offered a direct PC-to-PC transfer in Windows Backup, but as of 2026, Microsoft's support page says that feature is no longer available and points to Windows Backup instead.

**Copy files yourself:** Copy your user folders to an external drive and back, or move the old drive into the new PC as a data drive. [Remove an Old Windows Install and Keep Your Files](https://github.com/ImmuneMoon/Remove-Old-Windows-Install-Keep-Your-Files) shows how to clear the old Windows off it while keeping your files.

**Paid transfer tools:** Tools such as [Laplink PCmover](https://www.laplink.com/pcmover) move files, settings, user profiles, and many installed apps from one PC to another. Laplink says most apps it moves are ready to use, so expect to reinstall or reactivate a few, and have your license keys ready.

### 6.3 Reinstall your apps
* **winget:** install the apps from the list you saved in **Section 3**, replacing `D:` with your USB stick's letter. Apps that aren't available are reported and skipped.
  ```cmd
  winget import -i D:\apps.json --ignore-unavailable --accept-package-agreements
  ```
* **Ninite** installs many common free apps in one go. See [Installing Your Apps With Ninite](https://github.com/ImmuneMoon/Windows-Install-Guide#installing-your-apps-with-ninite).
* Install everything else from each maker's site, and sign back in to the apps you deactivated.

### 6.4 Keep big folders on a data drive
If your new Windows drive is small, move your Downloads, Documents, and Desktop folders to a data drive with each folder's **Location** tab. The [Migration Guide's Phase 5](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#2-relocate-windows-user-paths-to-secondary-hdds) walks through it.

## 7. Route A: Same PC, New Drive
Cloning copies your whole Windows drive onto the new one, so nothing needs reinstalling. Because the motherboard stays the same, Windows normally stays activated. Save your BitLocker recovery key first if encryption is on (**Section 3**).

The [Comprehensive Windows Migration and System Hardening Guide](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide) covers this in detail:

1. **Clone the drive:** [Phase 3](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#phase-3-bit-level-operating-system-migration) uses the free edition of DiskGenius, or your SSD maker's tool.
2. **Boot from the new drive:** [Phase 4](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#phase-4-uefi-boot-selection--c-drive-assignment) sets the boot order. Don't skip the [Critical Drive Collision Isolation Step](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#critical-drive-collision-isolation-step), because a clone and its original look identical to the PC.
3. **Free up space on the new drive:** [Phase 5](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#phase-5-ssd-space-reclamation--user-path-routing) moves your user folders to a data drive.

**Prefer a fresh install on the new drive?** Use [Remove an Old Windows Install and Keep Your Files](https://github.com/ImmuneMoon/Remove-Old-Windows-Install-Keep-Your-Files). It installs Windows on the new drive and clears the old Windows off the old one without touching your files.

## 8. Other Methods
These come up in searches. Here's what to know before you try them.

* **System image backup ("Backup and Restore (Windows 7)").** This Control Panel tool can still make a full image of your drive, but Microsoft has deprecated it and points people to third-party tools for full-disk backups. Restoring an image onto a different PC brings the same driver, storage mode, and activation issues as moving the drive (**Sections 4 and 5**).
* **Third-party imaging tools.** **Macrium Reflect Free** is retired: Macrium no longer adds features to it or supports it on newer Windows updates, so it's a poor choice for a new install. **Veeam Agent for Microsoft Windows** has a Free edition that needs no license, limited to one backup job saved to a local drive, a network shared folder, or a Veeam repository. An image restored onto new hardware still needs the steps in **Sections 4 and 5**.
* **Sysprep /generalize.** Sysprep strips a Windows install of its PC-specific details so it can be imaged and deployed to other PCs. It's a tool for PC makers and IT departments, and it isn't for home users:
  * Microsoft doesn't support running it on a Windows install that's already in use. It's only for preparing new installs for imaging.
  * Microsoft Store apps that were updated for one user make it fail.
  * Encrypted files and folders become unreadable for good.
  * It removes the PC from a work domain.

## 9. After the Move
- [ ] Windows is activated (**Settings** > **System** > **Activation**)
- [ ] Chipset, network, and graphics drivers are installed
- [ ] Windows Update has run until nothing new appears
- [ ] The clock shows the right time and date
- [ ] The BIOS is up to date, and the memory profile (**EXPO** or **XMP**) is turned on again
- [ ] Drive letters match your notes, and apps find their folders
- [ ] Folder links are recreated and project dependencies reinstalled, if you copied data to new drives (**Section 10**)
- [ ] Paid apps are signed in and activated
- [ ] Windows is stable. If anything is flaky, run the [DISM, SFC, and CHKDSK Windows Repair Guide](https://github.com/ImmuneMoon/DISM-SFC-CHKDSK-Windows-Repair-Guide)
- [ ] BitLocker is resumed if you suspended it: in **Manage BitLocker**, click **Resume protection**, or run `manage-bde -protectors -enable C:` as an administrator
- [ ] `manage-bde -status` shows encryption the way you want it: on with the recovery key saved, or off. See the [Migration Guide's Phase 7](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#6-microsoft-defender--drive-encryption)
- [ ] The old drives stay untouched for a few weeks, as a backup in case something turns up missing
- [ ] The old PC is wiped before you sell, donate, or recycle it: **Settings** > **System** > **Recovery** > **Reset PC** > **Remove everything**, with the option to clean the drive. On Windows 10, it's **Settings** > **Update & Security** > **Recovery** > **Reset this PC**
- [ ] If you moved a retail license, the old PC no longer uses it. A license that came with the old PC stays with it, so it can go to the next owner
- [ ] Still on Windows 10? Regular support ended on October 14, 2025. See [Where Windows 10 Stands Right Now](https://github.com/ImmuneMoon/Windows-10-Community-Support-Guide#where-windows-10-stands-right-now) in the Windows 10 Community Support Guide

## 10. Copy Your Data Drives to New Drives
A new PC is a good time to swap old data drives for bigger or faster ones. Windows' built-in **robocopy** command copies a whole drive, can be stopped and started again, and on each rerun copies only what changed.

### 10.1 Plan the copy

| Setup | Good for | Watch out for |
|---|---|---|
| **New drives in USB enclosures on the old PC** | You keep using the old PC while it copies, and the new drives go in already full. | USB is slow with lots of small files. Check the sector size first (**10.2**). |
| **Old drives on spare SATA ports in the new PC** | The fastest way: SATA to SATA. A drive doesn't need a bay for a temporary hookup. | The new PC has to be up and running. |
| **Old drives in a USB enclosure on the new PC** | Tidy, with no loose drives. | One drive at a time, and the slowest option. |

You can mix them: copy most of the data over USB while you still use the old PC, then finish the rest SATA to SATA in the new one.

* **Keep the same letters and paths.** If your files were in `D:\Projects`, make the new drive `D:` and keep the folders where they were. Game launchers, editors, shortcuts, and folders added to `PATH` all look for files by their full path.
* **Find what depends on each drive** before you retire it: game libraries (in Steam, **Settings** > **Storage**), apps installed there, and folders in your `PATH`. To see whether Microsoft Store apps use a drive, run `Get-AppxVolume` in PowerShell.
* **Expect small files to be slow.** Big files such as videos and games copy at roughly 70 to 250 GB an hour. Folders with millions of tiny files, such as code projects, can drop to a few GB an hour, especially from a 5,400 RPM drive. Start those days ahead so the last pass only copies changes, and skip folders you can rebuild (**10.3**).

### 10.2 Get the new drives ready
1. **Using a USB enclosure? Check the sector size first.** Some USB adapters present a drive with 4,096-byte sectors. A drive over 2 TB partitioned that way can look blank when you later connect it directly by SATA. In PowerShell:
   ```powershell
   Get-Disk | Select-Object Number, FriendlyName, BusType, Size, LogicalSectorSize
   ```
   **512** is safe. If it says **4096**, partition and fill the drive inside the new PC instead. A 3.5-inch enclosure needs its own power adapter switched on before the drive appears.
2. **Partition it.** In **Disk Management**, initialize the disk as **GPT**, right-click the unallocated space, and choose **New Simple Volume**. Format it as **NTFS**, and give it a spare temporary letter, such as `I:`, so it doesn't clash with your current drives.
3. **Stop USB drives from switching off.** Many 3.5-inch enclosures power off when Windows spins an idle disk down, after 20 minutes by default. For the migration, in an administrator Command Prompt:
   ```cmd
   powercfg /change disk-timeout-ac 0
   ```
   Set it back afterward with `powercfg /change disk-timeout-ac 20`.

### 10.3 Copy with robocopy
Save these lines as a `.cmd` file, then right-click it and choose **Run as administrator**. This example copies `D:` to a new drive at `I:`:
```cmd
robocopy D:\ I:\ /MIR /B /COPY:DAT /DCOPY:DAT /XJ /R:1 /W:1 /MT:8 ^
  /XD "$RECYCLE.BIN" "System Volume Information" ^
  /TEE /LOG:"%USERPROFILE%\Desktop\copy-D-log.txt"
```

| Option | What it does |
|---|---|
| `/MIR` | Makes the destination an exact copy, **including deleting anything there that isn't on the source.** Only point it at a new, empty drive, and check both letters twice. |
| `/B` | Reads files your account can't open, such as another user's folders. Needs an administrator window. |
| `/COPY:DAT /DCOPY:DAT` | Keeps file and folder dates. |
| `/XJ` | Skips junctions (folder links). Without it, robocopy can follow a link in a loop. See **Recreate folder links** below. |
| `/R:1 /W:1` | Retries a locked file once, after one second, instead of a million times. |
| `/MT:8` | Copies eight files at a time. |
| `/XD` | Skips folders. These two belong to Windows, and skipping them also stops `/MIR` deleting the new drive's own copies. |

robocopy finishes with a summary. Exit codes **0 to 7** mean success, and **8 or higher** means some files failed. The log lists them.

**Run it again whenever you like.** A rerun copies only new and changed files. Close apps that write to the drive, such as game launchers, editors, and sync apps, and run it one last time right before you move the drives. To stop a copy, press `Ctrl + C` in its window, and `Y` if it asks to end the batch job. The next run picks up where it stopped. If a copy window stops without a summary, run it again.

**Skip folders you can rebuild.** For code projects, leave out dependency and cache folders, and reinstall them after the move with `npm install` or `pip install -r requirements.txt`. Copy the projects folder with its own command, and add `/XD D:\Projects` to the main copy so it skips that folder:
```cmd
robocopy D:\Projects I:\Projects /MIR /COPY:DAT /DCOPY:DAT /XJ /R:1 /W:1 /MT:8 ^
  /XD node_modules .venv venv __pycache__ .next .turbo .parcel-cache ^
  .pytest_cache .mypy_cache .gradle
```
Only use this list on project folders. Installed apps, such as code editors, carry their own `node_modules` folders, and skipping those breaks the apps. A dependency folder that was half-copied by an earlier run stays on the new drive, because `/MIR` leaves skipped folders alone, so if a project misbehaves, delete its `node_modules` or `.venv` and reinstall.

**Recreate folder links.** `/XJ` skips junctions entirely, so links you made between folders, such as an app's data folder pointing at a project, won't exist on the new drive. Before the move, save a list of them from the old drive. This PowerShell command lists links without following them:
```powershell
Get-ChildItem D:\ -Recurse -Force -Attributes ReparsePoint -ErrorAction SilentlyContinue |
  Format-Table FullName, Target -AutoSize |
  Out-File "$HOME\Desktop\links.txt" -Width 500
```
After the last copy pass, recreate each one in a Command Prompt, with the link first and its target second:
```cmd
mklink /J "D:\Path\To\Link" "D:\Path\To\Target"
```
Recreate them only after your final pass. Don't run a `/MIR` copy onto a drive that already has links in it: the cleanup step can delete files on the far side of a link.

**A few files can't be copied, and that's fine.** When you copy an old Windows profile, the app shortcuts in `AppData\Local\Microsoft\WindowsApps`, such as `winget.exe`, fail with error 1920. So do socket files left by running apps. They only work inside a live Windows install, so nothing is lost.

### 10.4 Swap the drives
1. Run the last pass, then shut down and move the new drives in.
2. Unplug the old drive, so its letter is free. Then change the new drive to the old letter (**4.6**). Two drives of the same model can only be told apart by the serial number on the label (**Section 3**).
3. Open your apps and check they find their files.
4. Recreate your folder links and reinstall project dependencies (**10.3**).
5. Keep the old drives untouched for a few weeks, as a backup.

## 11. Troubleshooting

| What you see | Why | What to do |
|---|---|---|
| **INACCESSIBLE_BOOT_DEVICE** blue screen on the first boot | The new PC's storage controller or mode differs from the old one. | Set **AHCI** and turn off **Intel VMD** in the BIOS. If that's not possible, try the Safe Mode method in **4.4**, or do a clean install. |
| **BitLocker recovery** screen | Moving an encrypted drive to a new PC, a new motherboard with a new TPM, or a BIOS update while protection is on triggers BitLocker recovery. | Enter the 48-digit key from [aka.ms/myrecoverykey](https://aka.ms/myrecoverykey) whose key ID matches the screen. If it asks again on every start, suspend and resume protection once in **Manage BitLocker**. Suspend it before the next BIOS update (**4.7**). |
| **Drives are encrypted** on the new PC, though BitLocker was off on the old one | Windows 11 can turn on device encryption by itself on new hardware. File Explorer shows a padlock on those drives. | Save the recovery keys, or turn it off and block it (**4.5**). |
| **Windows isn't activated**, error **0x803F7001** | Windows couldn't find a valid license for this device. | Use the troubleshooter in **Section 5**, enter your product key, or buy a license. |
| Error **0xC004F213** | No product key was found, which often happens after a hardware change. | Use **I changed hardware on this device recently** in **Section 5**, or **Change product key**. |
| Error **0xC004C008** | The key has already been used on another device. | If you removed it from the old PC, use the Product Activation Portal or phone activation (**Section 5**, step 4). Otherwise, this PC needs its own license. |
| The troubleshooter **finds no devices** or can't reactivate them | Your account doesn't list this license against a device it recognizes. | Use the Product Activation Portal or phone activation (**Section 5**, step 4). |
| The **clock is hours off** on the first boot | The Windows Time service is stopped, so nothing corrects the new board's clock. | Start the service and resync (**4.5**). |
| **Only one monitor works** after changing graphics card brands | Until the new driver is installed, Windows uses Microsoft Basic Display Adapter, which drives one monitor. | Install the new card's driver. Plug monitors into the graphics card, because some boards' USB-C ports carry no video. |
| Windows asks you to **set up your PIN again** | A BIOS update reset the firmware TPM, where Windows Hello keeps its keys. | Set the PIN up again. This is expected (**4.7**). |
| **Case lighting doesn't respond** on the new board | The board's lighting controller may need a firmware update. | On the board's support page, look under **Utility** or **Firmware** for a lighting (RGB or LED) controller update, and update the BIOS. Only one app can control the lights at a time, so turn off **Dynamic Lighting** in **Settings** > **Personalization** if you use another lighting app. |
| A **USB enclosure disappears** during the copy | It switched off when Windows spun the idle disk down. | Switch it back on, and turn off disk sleep for the migration (**10.2**). |
| A **new drive over 2 TB looks blank** after moving it from a USB enclosure to SATA | The enclosure presented 4,096-byte sectors, and the drive was partitioned that way. | Put it back in the enclosure to read your files. Next time, check the sector size first (**10.2**). |
| **Copying project folders takes hours** | Millions of tiny files, mostly in dependency folders. | Skip dependency folders and reinstall them after the move (**10.3**). |
| **Links between folders are missing** after the copy | robocopy's `/XJ` skips junctions. | Recreate them with `mklink /J` (**10.3**). |
| **Troubleshoot** isn't on the Activation page | Windows is already activated, or you aren't signed in as an administrator. | Check the activation message. Sign in with an administrator account. |
| **No network** on the first boot | Windows has no driver for the new network chip. | Install the LAN or Wi-Fi driver from your USB stick (**Section 3**). |
| **Wrong drive letters**, or apps can't find their folders | Windows gave the drives new letters on the new hardware. | Change them back in **Disk Management** (**4.6**). |
| **The PC starts the old drive** or the wrong Windows | Two drives have Windows on them. A clone and its original look identical. | Set the boot order, and follow the [Critical Drive Collision Isolation Step](https://github.com/ImmuneMoon/Comprehensive_Windows_Migration_and_System_Hardening_Guide#critical-drive-collision-isolation-step). |
| Windows 11 says **TPM 2.0** or **Secure Boot** isn't enabled | It's turned off in the BIOS, or the PC is booting in Legacy or CSM mode. | Turn on **fTPM** or **Intel PTT** and **Secure Boot**, and switch to **UEFI** (convert with MBR2GPT first if the drive is MBR). Check the TPM by typing `tpm.msc` in the Run box. |
| **mbr2gpt** fails | The drive has more than three primary partitions or an extended partition, or a volume is still encrypted. | Suspend BitLocker and try again. If the partition layout is the problem, use a clean install instead. |
| `slmgr /dli` opens a folder | The Run box found the `C:\Windows\System32\slmgr` folder before the script. | Type `slmgr.vbs /dli` instead. |

## 12. Sources
**Activation and licensing**
* Microsoft Support: [Activate Windows](https://support.microsoft.com/en-us/windows/activate-windows-c39005d4-95ee-b91e-b399-2820fda32227), [Reactivating Windows after a hardware change](https://support.microsoft.com/en-us/windows/reactivating-windows-after-a-hardware-change-2c0e962a-f04c-145b-6ead-fb3fc72b6665) and [Get help with Windows activation errors](https://support.microsoft.com/en-us/windows/get-help-with-windows-activation-errors-09d8fb64-6768-4815-0c30-159fa7d89d85)
* Microsoft Learn, [Slmgr.vbs options](https://learn.microsoft.com/en-us/windows-server/get-started/activation-slmgr-vbs-options)
* Microsoft, [Windows 11 license terms](https://www.microsoft.com/en-us/useterms) (Section 4, Transfer) and [countries where transfer follows local law](https://aka.ms/transfer)

**BitLocker and encryption**
* Microsoft Support: [Find your BitLocker recovery key](https://support.microsoft.com/en-us/windows/find-your-bitlocker-recovery-key-6b71ad27-0b89-ea08-f143-056f5ab347d6), [Back up your BitLocker recovery key](https://support.microsoft.com/en-us/windows/back-up-your-bitlocker-recovery-key-e63607b4-77fb-4ad3-8022-d6dc428fbd0d) and [Device encryption in Windows](https://support.microsoft.com/en-us/windows/device-encryption-in-windows-cf7e2b6f-3e70-4882-9532-18633605b7df)
* Microsoft Learn: [BitLocker device encryption](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/) (automatic device encryption and the `PreventDeviceEncryption` setting)
* Microsoft Learn: [BitLocker recovery overview](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/recovery-overview), [BitLocker operations guide](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/operations-guide) and [manage-bde protectors](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/manage-bde-protectors)

**Firmware, disks, and booting**
* Microsoft Support: [Windows 11 system requirements](https://support.microsoft.com/en-us/windows/experience/compatibility/windows-11-system-requirements), [Enable TPM 2.0 on your PC](https://support.microsoft.com/en-us/windows/enable-tpm-2-0-on-your-pc-1fd5a332-360d-4f46-a1e7-ae6b0c90645c) and [Windows 11 and Secure Boot](https://support.microsoft.com/en-us/windows/windows-11-and-secure-boot-a8ff1202-c0d9-42f5-940f-843abef64fad)
* Microsoft Learn: [MBR2GPT](https://learn.microsoft.com/en-us/windows/deployment/mbr-to-gpt), [Boot to UEFI mode or legacy BIOS mode](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/boot-to-uefi-mode-or-legacy-bios-mode), [Stop error 7B or Inaccessible_Boot_Device troubleshooting](https://learn.microsoft.com/en-us/troubleshoot/windows-client/performance/stop-error-7b-or-inaccessible-boot-device-troubleshooting), [BCDEdit /set](https://learn.microsoft.com/en-us/windows-hardware/drivers/devtest/bcdedit--set), [shutdown](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/shutdown), [Change a drive letter](https://learn.microsoft.com/en-us/windows-server/storage/disk-management/change-a-drive-letter) and [Viewing hidden devices](https://learn.microsoft.com/en-us/windows-hardware/drivers/install/viewing-hidden-devices)
* Intel, [Unable to install the Intel Rapid Storage Technology driver in AHCI mode](https://www.intel.com/content/www/us/en/support/articles/000089248/technologies/intel-rapid-storage-technology-intel-rst.html)
* Dell, [Switching SATA modes: AHCI to RAID on Dell Data Security Windows computers](https://www.dell.com/support/kbdoc/en-us/000124714/how-to-switch-from-ahci-to-raid-on-dell-data-security-windows-systems)

**Drivers, the clock, and drive letters**
* Microsoft Learn: [Microsoft Basic Display Driver](https://learn.microsoft.com/en-us/windows-hardware/drivers/display/microsoft-basic-display-driver), [Windows Time service tools and settings](https://learn.microsoft.com/en-us/windows-server/networking/windows-time-service/windows-time-service-tools-and-settings), [Set-Partition](https://learn.microsoft.com/en-us/powershell/module/storage/set-partition) and [Get-PhysicalDisk](https://learn.microsoft.com/en-us/powershell/module/storage/get-physicaldisk)
* Wagnardsoft, [Display Driver Uninstaller (DDU)](https://www.wagnardsoft.com/display-driver-uninstaller-ddu-)

**Copying data drives**
* Microsoft Learn: [robocopy](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/robocopy), [mklink](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/mklink) and [Powercfg command-line options](https://learn.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options)

**Moving files, settings, and apps**
* Microsoft Support: [Back up and restore with Windows Backup](https://support.microsoft.com/en-us/windows/backup-and-restore-with-windows-backup-87a81f8a-78fa-456e-b521-ac0560e32338), [Transfer your files and settings to a new Windows PC](https://support.microsoft.com/en-us/windows/experience/backup-recovery/transfer-your-files-and-settings-to-a-new-windows-pc) and [Reset your PC](https://support.microsoft.com/en-us/windows/reset-your-pc-0ef73740-b927-549b-b7c9-e6f2b48d275e)
* Microsoft Learn: [winget export](https://learn.microsoft.com/en-us/windows/package-manager/winget/export) and [winget import](https://learn.microsoft.com/en-us/windows/package-manager/winget/import)
* [Laplink PCmover](https://www.laplink.com/pcmover)

**Other methods**
* Microsoft Learn: [Deprecated features in the Windows client](https://learn.microsoft.com/en-us/windows/whats-new/deprecated-features) (System Image Backup), [Sysprep overview](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--system-preparation--overview) and [Sysprep (generalize) a Windows installation](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--generalize--a-windows-installation)
* Macrium, [Product support policy](https://www.macrium.com/product-support-policy)
* Veeam, [Veeam Agent for Microsoft Windows product editions](https://helpcenter.veeam.com/docs/agentforwindows/userguide/license_editions.html)

<!-- guide:end -->

## ☕ Support the Project

If you find this project helpful and want to support further development by Fulllion Creative Works, consider leaving a tip!

* [Donate via PayPal](https://www.paypal.com/donate/?hosted_button_id=LCDZX75HR4CLC)
* [Support on Ko-fi](https://ko-fi.com/fulllion)

---
© 2026 Fulllion Creative Works. All rights reserved.

# 📱 Rooting Guide for Redmi 9 Activ (Codename: Cattail)

## 🔰 Introduction

What's up newbies,  
Before we dive in, **make sure this guide is for your specific device**. (Skip this part if you're sure.)

> ⚠️ This guide only covers:
- **Device**: Redmi 9 Activ  
- **Also known as**: Redmi 9C  (CATTAIL)
- **Codename**: cattail  
- **Region**: India  
- **MIUI Version**: 12.0.8.0  
- **Android Version**: 10

> ❌ This guide does **not** cover:
- Redmi 9 (codename: *lancelot*)  
- Redmi 9A  
- Redmi 9C (codename: *angelica* / *anglican*)

If you follow the guide correctly, you'll be able to root your device.

⚠️ **Disclaimer**: The author is not responsible for any damage caused to your device during or after rooting. Rooting can be risky — apps with root access may modify system-level files.

---

## 🔓 Step 1 – Unlocking the Bootloader  
*(Skip if already unlocked)*

> ⚠️ Unlocking bootloader wipes all data and may void your warranty.

1. **Enable Developer Options**  
   Go to: `Settings → About phone → Tap "MIUI version" 7 times`
2. **Enable USB Debugging + OEM Unlocking**  
   Go to: `Settings → Additional settings → Developer options`  
   Enable:
   - ✅ OEM unlocking  
   - ✅ USB debugging
3. **Bind Your Mi Account**  
   Tap `Mi Unlock status` → `Add account and device`
4. **Download Mi Unlock Tool**  
   Get it from [Mi Unlock Tool](https://en.miui.com/unlock/)  
   Extract the ZIP and run `miflash_unlock.exe` on PC.
5. **Boot your phone into Fastboot mode**
6. **Connect phone to PC via USB**
7. **Use Mi Unlock Tool**  
   - Log in using the same Mi Account  
   - Click **Unlock** and wait for completion

✅ **Boom! Bootloader unlocked.**

---

## ⏭️ Skip Alert!

> If you already have a **patched boot.img**, you can skip **Step 2 & 3**

---

## 📦 Step 2 – Getting the `boot.img` File

- You can download already patched and extracted boot.img from the releases section or....
- Download **Redmi 9 Activ boot.img** from a trusted source.  
- Or extract it yourself from the official **Fastboot ROM**:  
  [MIUI V12.0.18.0 Fastboot ROM](https://xmfirmwareupdater.com/miui/cattail/stable/V12.0.18.0.QCTINXM/) (~2.6 GB)  
  Extract the archive multiple times until you get `boot.img`.
---

## 🧙‍♂️ Step 3 – Patching `boot.img` for Root

1. Download **official Magisk**: [Magisk Releases](https://magisk.me/releases/)
2. Open the Magisk app
3. Tap **Install** under Magisk section
4. Choose: `Install → Select and Patch a File → boot.img`
5. Magisk will create a **patched `boot.img`**

---

## ⚡ Step 4 – Flashing the Patched `boot.img`

### 📱 Using Another Android Phone  
(Tested on Android 10; not recommended for Android 11+ as OTG support may break the process)

1. Install **Bugjaeger** app on the other phone  
2. Connect both phones using OTG  
   - OTG's **microUSB** goes into the **other** phone  
   - Your phone's **data cable** plugs into **your (target) device**
3. When prompted, allow the OTG connection
4. Open **Bugjaeger** → tap **Reboot Bootloader**
5. Once in bootloader:
   - Tap ⚡ icon → Open **Terminal**
   - Enter the command:  
     ```sh
     adb reboot bootloader
     fastboot flash boot <select patched_boot.img>
     ```
 Here's how to select the file in Bugjaeger:

![Selecting boot.img in Bugjaeger](how_to_add_file.mp4)

---

### 💻 Using a PC or Laptop  
_Works on Linux & Windows_

1. **Get Platform-Tools**
    
    - Download from: [Android SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools)
        
    - Pick your OS → Extract the ZIP somewhere easy (like Desktop)
        
2. **Prep the Patched Boot.img**
    
    - Copy your patched `boot.img` into the same folder as `platform-tools` (makes life easier 😉)
        
    - Or note the full path if it’s elsewhere.
        
3. **Open Terminal / Powershell**
    
    - Linux: Open terminal in the platform-tools folder (`cd /path/to/platform-tools`)
        
    - Windows: Shift + Right Click → **Open PowerShell window here**
        
4. **Connect your phone**
    
    - Plug it into PC via USB
        
    - Make sure **USB Debugging** is enabled
        
    - Select **No Data Transfer** on the phone
        
5. **Reboot into Bootloader**
    
    ```sh
    adb reboot bootloader
    ```
    
6. **Flash the Patched Boot.img**
    
    - Linux:
        
        ```sh
        ./fastboot flash boot /full/path/to/patched_boot.img
        ```
        
    - Windows:
        
        ```sh
        .\fastboot flash boot C:\full\path\to\patched_boot.img
        ```
        
7. **Reboot your device**
    
    ```sh
    fastboot reboot
    ```


---

## ✅ Done! Reboot your phone — it's now rooted!

> 🎉 **Congratulations! You've successfully rooted your Redmi 9 Activ!**

---

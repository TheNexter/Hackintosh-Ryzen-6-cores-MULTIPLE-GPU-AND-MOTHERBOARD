# Hackintosh Opencore for Ryzen 3600 WITH B550 / B450 + AMD RX 6600-XT / 6800 / 6800XT / RX 6900XT / RX 480 / RX 580

I have publish my lastest ever EFI for 13.2 Ventura. I stop to update this repo guy because i sell my computer.
If anyone of you can make a fork and continue to maintain EFI sometime i am gonna reference your repo just here.

NEED 4/5 REBOOT TO BOOT in MY CASE SOMETIMES

EFI is ready for linux, macos and windows

## My default Build

* **CPU:** AMD Ryzen 3600
* **Motherboard:** ASUS PRIME B550M-A (WI-FI)
* **Memory:** 16 GB
* **Storage (macOS):** 500GB NVME
* **Storage (Windows):** 250GB SATA
* **Video Card:** Gigabyte AMD RX 6600-XT

If your Motherboard is not the same B550 or B450 check if your RJ45 port and jack port is Realtek and now normaly it's good

✅ **Working :**

All (include WIFI and bluetooth + iService like imessage, icloud, facetime...)

❌ **Not Working :**

Airdrop and Microphone jack

Bios settings :
Restore to default settings and above 4G NEED TO BE TURN ON + RESIZE BAR ON:
![image](https://user-images.githubusercontent.com/17613028/145913588-a78efc7a-dfaf-47d7-b35d-1b25f42d8231.png)


## Installation :
**For everyone of you :**

Download latest version on my github to have my EFI

Install [python3](https://www.python.org/downloads/ "python3")
Download [Propertree](https://github.com/corpnewt/ProperTree "Propertree") with download ZIP
![image](https://user-images.githubusercontent.com/17613028/145912137-d2ee52d7-760a-45a6-856f-f3bed810654c.png)

open terminal and type cd and drag and drop folder "Scripts" inside terminal, press enter and now type : python3 buildapp-select.command
3 like me ![image](https://user-images.githubusercontent.com/17613028/145912648-151dd5f8-863e-4266-a166-44306bb93119.png)

try everyone if blackscreen

Change your system serial numbers, board numbers and UUID numbers with **iMacPro1,1**

Tutorial :
Stop the video at 3:36 it's good https://youtu.be/vBRrCYZEjtI

Do not forget to save your file

Check next things in Installation, it's maybe for you and after Go to USB EFI SETTINGS part of documentation

**For SATA SSD INSTALLATION :**

Working with sata SSD, just remove the line >
![image](https://user-images.githubusercontent.com/17613028/145910303-7ec1593c-1af7-4a2e-a951-0f325e5886f7.png)

Do not forget to save your file

**For non WIFI MOTHERBOARD :**

Remove AirportItlwm.kext and itlwm.kext  ![image](https://user-images.githubusercontent.com/17613028/145911904-08751532-eca4-4f2e-8fdd-74984eba6bf7.png)

Open Propertree, open config.plist and Press CMD + R go inside folder name OC and click choose
![image](https://user-images.githubusercontent.com/17613028/145913301-b62ddcc1-f7a0-4d5d-8225-01c6b457dba8.png)

And now do CMD + SHIFT + R select again folder name OC and click choose

Do not forget to save your file

**For B450 Motherboard :**

Remove SSDT-CPUR.aml
![image](https://user-images.githubusercontent.com/17613028/145916554-06b24c6b-d3aa-4b9c-87ed-a6a2930ec570.png)

Open Propertree, open config.plist and Press CMD + R go inside folder name OC and click choose
![image](https://user-images.githubusercontent.com/17613028/145913301-b62ddcc1-f7a0-4d5d-8225-01c6b457dba8.png)

And now do CMD + SHIFT + R select again folder name OC and click choose
Turn ON SetupVirtualMap inside :
![image](https://user-images.githubusercontent.com/17613028/145916805-f075d77e-7234-481a-a80e-d8684e322ec1.png)

Do not forget to save your file

**For RX 480 / RX 580 GPU**

Remove "agdpmod=pikera"
![image](https://user-images.githubusercontent.com/17613028/145915060-718005df-c23e-41bc-9756-b93db8c72fdf.png)

Do not forget to save your file

**USB EFI SETTINGS**

Install MacOS Monterey on your USB KEY :

https://www.youtube.com/watch?v=RJkiFJwzos4

Download MountEFI ZIP (like we did with Propertree)

Open the folder MountEFI-update

Do right click to open MountEFI.command

Select USB installer key
![image](https://user-images.githubusercontent.com/17613028/145914385-900d8481-ac65-4f3f-9870-8a1cb619d8da.png)

Type your password

And now go inside Finder > EFI and here place your folder EFI
![image](https://user-images.githubusercontent.com/17613028/145914475-82171215-c8ee-4289-8a44-31d0c7fb8b5e.png)

If your MacOS run perfectly it's time to save this key in good place but before we need to copy EFI Folder where is now inside your USB key to your SSD to be ok to boot without usb, and in the futur, test your new EFI settings inside your SSD, not inside your USB, your USB is your backup EFI + Reinstall USB key

To copy EFI folder to EFI SSD > Open MountEFI, open USB key + MacOS

Now you have 2 EFI partition inside your Finder, copy EFI folder to empty partition EFI, try to restart without USB key


**DEBUG :**

Audio stop at 3:50: https://youtu.be/GXft2j0s4Gg

Microphone Jack > impossible to work, buy USB one :(

SSD NVME is external > Be sure you do not have remove "PciRoot(0x0)/Pci(0x1,0x1)/Pci(0x0,0x0)" inside your config.plist > DeviceProperties > Add > PciRoot(0x0)/Pci(0x1,0x1)/Pci(0x0,0x0) > built-in
![image](https://user-images.githubusercontent.com/17613028/145917296-9b49f957-424c-4e38-bb6c-0c9d2d0a0e71.png)

Your NVME continue to be external ssd ? it's ok, install macos inside sata hard drive or sata ssd and download [hackintool](https://github.com/headkaze/Hackintool/tagshttp:// "hackintool")

click on the last version and download Hackintool.zip

Now open Hackintool in right click inside your Finder

Go inside PCIe, find your NVME SSD

Copy device path
![image](https://user-images.githubusercontent.com/17613028/145917923-6bc78dad-ad6e-4eaa-9ef2-8fb293c1df85.png)

Open config.plist with propertree and do like me but with your path

![image](https://user-images.githubusercontent.com/17613028/145918147-db118db0-7726-40aa-8726-b9d2861b6b08.png)

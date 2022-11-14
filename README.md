# Asus Rog Strix G531GD 💻 - OpenCore EFI

Ready to use OpenCore EFI folder which will help to install macOS in Asus Rog Strix G531GD only. If your laptop/PC has similar specifications to compare 
to Rog Strix G531GD then you can edit the EFI folder on your own by taking reference of 
[OpenCore](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html) package.
But I recommend creating EFI on your own with the help of [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html) package.


## 🛠 Laptop Specifications

**Model Name:** Asus Rog Strix G531GD

**Bios Mode:** UEFI

**RAM:** 8 GB (DDR4)

**Storage:** 512 GB SSD

**Processor:** Intel® i5 9300H [(Coffee lake plus)](https://www.reddit.com/r/hackintosh/comments/mc1bvn/what_is_coffee_lake_plus/)

**Processor Graphics:** Intel® UHD Graphics 630

**Dedicated Graphics:** NVIDIA GeForce GTX 1050

**Ethernet:** Realtek PCIe GbE 

**WiFi (wireless card):** Intel(R) Wireless-AC 9560

**Sound card:** Realtek ALC294


##  📸 Screenshot

![ROG](https://user-images.githubusercontent.com/82045747/201528162-b4cf1571-dbce-4d27-a0eb-2fd9a8e819a9.png)

##  ⚠️ Following things are not working 

On my laptop, below listed things are not working:

- ❌ Right Click

if you find more things which are not mentioned here then please let me know.

##  🆗 Following things are properly working 

listed below things are properly working:

- ✅ Wi-FI
- ✅ Speakers & Audiojack
- ✅ Bluetooth
- ✅ Trackpad
- ✅ Trackpad gestures
- ✅ USB ports
- ✅ RGB backlight

many more things are working but the listed items are more important.
## 🔎 Required items for installation of macOS

- 100GB of free space in SSD or external SSD drive
- 32GB Pendrive
- [MiniTool Partition Wizard](https://www.partitionwizard.com/free-partition-manager.html)
- [balenaEtcher](https://www.balena.io/etcher/)
- [Explorer++](https://explorerplusplus.com/download)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- [ProperTree](https://github.com/corpnewt/ProperTree)
## 💾 How to flash USB drive

- ⚠️ Note: This method is working for me. If it is not working for you then you can also follow the official [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html) process. This methos is suitable for windows users only.

- first of all download the `macOS Ventura` image file in `.raw` or `.dmg` file format from `Hackintosh community shop` or from wherever you want.

- Then after insert your USB drive and open [balenaEtcher](https://www.balena.io/etcher/). Now select the USB drive and flash the `macOS Ventura` file which is downloaded earlier.

- After that, open [MiniTool Partition Wizard](https://www.partitionwizard.com/free-partition-manager.html) and find the EFI partition of the USB drive which you flash earlier.

- Then right-click on the EFI partition and select assign letter. Next, assign any letter to the selected partition and click on apply button. Now you can see the EFI partition of the USB drive in `My Computer` but can not open that partition.

- Now open [Explorer++](https://explorerplusplus.com/download) as Run as an administrator. After that, go to the EFI partition of the USB drive and delete the EFI folder.

- Now download my EFI folder and [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). After that, open [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) folder then run the `GenSMBIOS.bat` file and enter the number accordingly where the `Generate SMBIOS` option is given.<br/><br/>
![1](https://user-images.githubusercontent.com/82045747/197948538-8845e261-9408-42c1-ae34-e61a0dcd07ea.png)

- Now enter `MacBookPro16,4` and don't close this window.<br/><br/>
![2](https://user-images.githubusercontent.com/82045747/197950048-2eab6072-2c0b-4783-b6fc-f418d316a67f.png)

- Then after download [ProperTree](https://github.com/corpnewt/ProperTree) and open folder and run `ProperTree.command` file. Then click on the file then click on open. After that navigate to the EFI folder which you download from this repository and then go to the `EFI > OC > config.plist` and open it.<br/>

- Now first of all right click on `Root` and click on `Collapse ALl`. Then click on `Root > PlatformInfo > Generic`<br/><br/>
![3](https://user-images.githubusercontent.com/82045747/197954073-7d9d6c85-7e31-459c-a538-61f2500b7ade.png)

- Then after replacing existing fields with new fields which you generated earlier through GenSMBIOS.<br/><br/>
![4](https://user-images.githubusercontent.com/82045747/197955557-148bece1-a096-466d-9a72-81001043ebe3.png)

- Double-click on the values fields which are highlighted and replace them with the given table.

| Existing Field Name | Replace with |                        
| -------- | ------------ |
| MLB| Board Serial |
| SystemSerialNumber| Serial |
| SystemUUID | SmUUID |

for example, we want to change the MLB value in `config.plist` then double click on the value field of MLB and delete it now copy the Board Serial value from another GenSMBIOS terminal and paste it in the MLB value field. Replace all 3 values with new values.

- Then after saving the file and close all windows.

- Now copy the EFI folder and open Explorer++ with Run as administrator and navigate to the EFI partition and paste the EFI folder.

- At this stage, you have ready to install a USB drive for mac installation. Change your BIOS settings respectively (Self-research requires 🤓).  

- Make a 100GB partition and boot it into a USB drive and install macOS. watch the YouTube video for the installation process.

- Note: Changing PlatformInfo is very important otherwise iCloud services will not work.

## 🖥 Post Installation

Run the following command in the terminal after successful installation. It might require some `kext` for working properly.

```bash
  sudo kextcache -i /
```
![5](https://user-images.githubusercontent.com/82045747/197967301-a64b907b-13a6-49f9-8161-de5f8faea98d.png)<br/>

Now download and install the following application in macOS for RGB Backlight.

- [RogSwitch](https://github.com/black-dragon74/ROGSwitch)
 ```bash
  https://github.com/black-dragon74/ROGSwitch

```

- [macAura](https://github.com/serdeliuk/macAura)
 ```bash
  https://github.com/serdeliuk/macAura
```
After successfully installing, open macAura and configure it.

- Internal Speakers will not work if you haven't disable boot sound. [Click here](https://www.asus.com/global/support/FAQ/1036483/) to see how to disable boot sound. After disabling boot sound your Speakers will work perfactly
## 💿 How to boot without a USB drive and Dual boot with windows?

- Follow the steps given in the photos and create an EFI partition.<br/>
![1](https://user-images.githubusercontent.com/82045747/198231379-d527b1e1-98ad-43d4-a4c8-dce7f35174c9.png)<br/>
![2](https://user-images.githubusercontent.com/82045747/198234115-6b8b8507-9770-4686-8ce6-1162f51fe27a.png)<br/>
![3](https://user-images.githubusercontent.com/82045747/198231388-00c81dfa-3af3-43f8-ac3c-8ebe58ca1e87.png)<br/>
![4](https://user-images.githubusercontent.com/82045747/198231411-f412b0ed-638c-4c09-872b-27300c169bc4.png)<br/>
![5](https://user-images.githubusercontent.com/82045747/198231438-a99718ec-df58-4499-a702-7980715d770a.png)<br/>
- After you created the EFI partition, switch to windows and open [MiniTool Partition Wizard](https://www.partitionwizard.com/free-partition-manager.html) then assign any letter to the `EFI` Partition which you have created in macOS.

- Now copy the EFI folder from the USB drive and paste that EFI folder into the `EFI` partition which you created by using macOS.

- After that, remove the USB drive, go to the BIOS setting, go to the BOOT priority, and move down windows as second and MS-DOS volume as first.

- Now you can boot into both the OS without USB drive
##  📝 Feedback

If you have any feedback or queries, please reach out to gautamkantesariya@outlook.com
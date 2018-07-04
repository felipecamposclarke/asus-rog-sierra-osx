# MacOS High Sierra 10.13.5 Guide for Asus ROG GL502VS

After a few days of fighting, I finally have Mac OSX High Sierra running on this laptop.

### Specs:
* CPU : Intel Core i7-7700 (Kaby Lake)
* Integrated Graphics : Intel HD 520
* Dedicated Graphics : Nvidia GTX1060
* RAM : 16 GB DDR4 2133 MHz (soldered)
* SSD : 128 GB Toshiba CV3-8D256 (M.2 2280 SATA, replaceable. Not compatible with NVMe SSD)
* Screen : 13.4-inch 1920 x 1080 IPS Matte display
* Battery : 4-cell Lithium-Ion 3220 mAh 10 hours
* Ports : 1xUSB 3.1 Gen-1 Type-C, 3xUSB 3.0, 1xUSB 2.0, 1xHDMI (full-size), 1xAudio jack
* Wifi/Bluetooth : Atheros QCNFA344A (ven id:168c, dev id:003e), (M.2 NGFF)
* Audio : ALC255 (ven id:10ec, dev id:0255)
* SD Card Reader : Realtek USB2.0-CRW (ven id:0bda, dev id:0129)
* Back-lit keyboard
* Trackpad i2c (protocl ELAN1200)

### Working:
* Battery
* Sleep
* QE/CI (Nvidia Web Driver)
* Keyboard + Backlight
* USB 2.0/3.0
* SSD
* HDD
* Speakers and internal mic
* WebCam
* Wi-fi (replace with USB card)
* Ethernet
* HDMI
* Display Port

### Not yet working:
* Touchpad / ELAN1200
* Stock Wi-fi
* Brightness Control (alternative: use Brightness Slider app from App Store)
* Keyboard Backlight Control (fn+F3 / F4 not works)

### Not tested:
* SD Card slot
* Display by USB-C



## Before installation

### BIOS(UEFI) configuration:

Access the BIOS setup by pressing F2 then select Advence Configuatión by pressing F7

### Build your USB installer

1. Download Hig Sierra via the Mac App Store https://itunes.apple.com/cl/app/macos-high-sierra/id1246284741?mt=12
2. Create installer usb using Unibeast http://www.unibeast.com. The version used is this
3. Mount the usb drive's EFI partition to edit its content. When you finish installing with Unibest the partition is already mounted, but if you need to access again in the future you can use Clover Configurator, EFI Mounter v3 or simply use the terminal
4. Edit the EFI/CLOOVER/config.plist file that is inside the EFI partition. You can edit it with Clover Configurator, but the patch that was necessary to boot the installer was not available in the interface. I simply opened the file and edited it with my favorite text editor. The only change you made was to change the 'FixHeaders' entry to true. The resulting configuration file is this
5. puts the SATA-100-series-unsupported.kext and SATA-200-series-unsupported.kext on EFI/CLOOVER/kexts/Others folder (Required to recognize the HDD)

After these steps, we are ready to install the operating system!!!!!

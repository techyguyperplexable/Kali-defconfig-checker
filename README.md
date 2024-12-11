# RE-purposed defconfig checker 

defconfig checker and enabler for kali nethunter

## Use 

Clone this repo then go to kernel source and grab your defconfig from /arch/arm64/configs and place your defconfig in this repo and run the following command

./check-kernel-config name-of_defconfig -w

Example: ./check-kernel-config gki_defconfig -w

NOTE: For certain kernel functions to work properly including SDR, wifi adapters and bluetooth spamming, spoofing and attacks, you will need to set up moduling. 

Due to conflicts in wifi adapter drivers all must be made into modules so that you can use rmmod and insmod to unload and load the modules for those adpters.

Kali Nethunter will NOT function using a monolithic kernel and firmware will not load for adapters using such


Below are the drivers that you will need to change from =y to =m 



SDR 

CONFIG_USB_AIRSPY=m

CONFIG_USB_HACKRF=m

CONFIG_USB_MSI2500=m



bluetooth spoofing, spamming and attacks

CONFIG_BT_HCIVHCI=m



Wireless network adapters 

CONFIG_MT7601U=m

CONFIG_RT2X00=m

CONFIG_RT2500USB=m

CONFIG_RT73USB=m

CONFIG_RT2800USB=m

CONFIG_RT2800USB_RT33XX=m

CONFIG_RT2800USB_RT35XX=m

CONFIG_RT2800USB_RT3573=m

CONFIG_RT2800USB_RT53XX=m

CONFIG_RT2800USB_RT55XX=m

CONFIG_RT2800USB_UNKNOWN=m

CONFIG_RTL8187=m

CONFIG_RTL_CARDS=m

CONFIG_RTL8192CU=m

CONFIG_RTL8XXXU_UNTESTED=m



Once these steps are taken replace your old defconfig with the new one build and profit




# RE-purposed defconfig checker 

defconfig checker and enabler for kali nethunter

## Use 

Clone this repo then go to kernel source and grab your defconfig from /arch/arm64/configs and place your defconfig in this repo and run the following command

./check-kernel-config name-of_defconfig -w

Example: ./check-kernel-config gki_defconfig -w

NOTE: For certain kernel functions to work properly including SDR, wifi adapters and bluetooth spamming, spoofing and attacks, you will need to set up moduling. 

Due to conflicts in wifi adapter drivers all must be made into modules so that you can use rmmod and insmod to unload and load the modules for those adpters.

Kali Nethunter will NOT function using a monolithic kernel. 

Below are the drivers that you will need to change from =y to =m 

SDR 

CONFIG_USB_AIRSPY
CONFIG_USB_HACKRF
CONFIG_USB_MSI2500

bluetooth spoofing, spamming and attacks

CONFIG_BT_HCIVHCI

wireless network adapters 

CONFIG_MT7601U
CONFIG_RT2X00
CONFIG_RT2500USB
CONFIG_RT73USB
CONFIG_RT2800USB
CONFIG_RT2800USB_RT33XX
CONFIG_RT2800USB_RT35XX
CONFIG_RT2800USB_RT3573
CONFIG_RT2800USB_RT53XX
CONFIG_RT2800USB_RT55XX
CONFIG_RT2800USB_UNKNOWN
CONFIG_RTL8187
CONFIG_RTL_CARDS
CONFIG_RTL8192CU
CONFIG_RTL8XXXU_UNTESTED

Once these steps are taken replace your old defconfig with the new one build and profit

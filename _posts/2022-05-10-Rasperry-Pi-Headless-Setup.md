---
title: Setting Up A Headless Raspberry Pi
author: Sam
date: 2022-05-10 08:00:00 +0000
categories: [Hardware, Raspberrypi]
tags: [hardware,raspberrypi,hacking]     # TAG names should always be lowercase
comments: false
---

# Intro


# Wi-Fi Setup

To setup a Wi-Fi connection on your headless Raspberry Pi, create a text file called wpa_supplicant.conf and place it in the root directory of the microSD card. You will need the following text in the file.

```bash
country=UK
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
	scan_ssid=1	
	ssid="your_wifi_ssid"
	psk="your_wifi_password"
	key_mgmt=WPA-PSK
}
```

# Power Optimisation

## Disable the USB Controller

**Power Saved?** Approximately 100mA.

To disable the USB controller on your Raspberry Pi execute the following command:

`echo '1-1' |sudo tee /sys/bus/usb/drivers/usb/unbind`

To re-enable the USB controller when it’s needed again:

`echo '1-1' |sudo tee /sys/bus/usb/drivers/usb/bind`

**After a reboot the USB controller will be enabled automatically.**

**N.B. I thought this was a great way to save power on my upcoming project...then remembered I'm using a USB powered Wi-Fi adapter** :man_facepalming:



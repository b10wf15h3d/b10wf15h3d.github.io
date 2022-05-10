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

Dependent on your model Raspberry Pi these are the estimated power consumption figures:

| Model | IDLE | LXDE Loaded | 1080 resolution video | 400% CPU Loaded |
| --- |---| --- | ---| --- |
| Raspberry Pi 4B |	575 mA | 885 mA |	600 mA |1280 mA |
| Raspberry Pi 3B+ | 400 mA | 690 mA | 510 mA | 980 mA |
| Raspberry Pi Zero W |	120 mA	| 160 mA | 170 mA – |
| Raspberry Pi Zero | 100 mA | 140 mA | 140 mA – |

If you're running a project whereby your device is running off an external battery then every ounce of power saved counts!

## Disable the USB Controller

**Power Saved?** Approximately 100mA.

To disable the USB controller on your Raspberry Pi execute the following command:

`echo '1-1' |sudo tee /sys/bus/usb/drivers/usb/unbind`

To re-enable the USB controller when it’s needed again:

`echo '1-1' |sudo tee /sys/bus/usb/drivers/usb/bind`

**After a reboot the USB controller will be enabled automatically.**

**N.B. I thought this was a great way to save power on my upcoming project...then remembered I'm using a USB powered Wi-Fi adapter** 🤦🏻‍♂️

## Disable HDMI Output

**Power Saved?** Approximately 30mA.

To disable the HDMI output on your Raspberry Pi, execute the following command:

`sudo /opt/vc/bin/tvservice -o`

To re-enable the HDMI output when you need it back use this command:

`sudo /opt/vc/bin/tvservice -p`

**After a reboot HDMI output is enabled automatically**

## Disable Wi-Fi and Bluetooth

**Power Saved?** Approximately 40mA.

If your solution isn’t using Wi-Fi or Bluetooth, you can disable them or just one of them.

To disable Wi-Fi and Bluetooth, open /boot/config.txt, add these parameters, and reboot:

```
[all]
dtoverlay=disable-wifi
dtoverlay=disable-bt
```

To re-enable Wi-Fi and Bluetooth (or just one of them), simply remove the parameter(s) from the file and reboot.

## Disable Onboard LEDs

**Please note that these configurations are specific to the Raspberry Pi 4 Model B.**

**Power Saved?** Approximately 10mA.

We can disable the onboard LEDs on the Pi by again editing the /boot/config.txt file, adding the following, and rebooting:

### Disable the PWR LED

```
dtparam=pwr_led_trigger=none
dtparam=pwr_led_activelow=off
```

### Disable the Activity LED

```
dtparam=act_led_trigger=none
dtparam=act_led_activelow=off
```

### Disable ethernet port LEDs

```
dtparam=eth_led0=4
dtparam=eth_led1=4
```


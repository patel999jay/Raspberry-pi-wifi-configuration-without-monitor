# Raspberry-pi-wifi-configuration-without-monitor
Raspberry pi wifi configuration without monitor

# How to Set up WiFi on Your Raspberry Pi without Monitor ?

Here is the solution. 

# What you need :
```bash
1. Here's everything you'll need to complete this : Raspberry Pi	
```
## Step 1: Put the Raspbian SD card into your computer.
## Step 2: Navigate to the boot directory.
You'll have to locate the boot directory, on my Mac it's in /Volumes/boot.
```bash
cd /Volumes/boot	
```
## Step 3: Add your wpa_supplicant.conf file

### For Raspbian Jessie:
Create a file in this directory called wpa_supplicant.conf. The file should contain the following details:
```bash
network={
    ssid="YOUR_NETWORK_NAME"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}	
```

### For Raspbian Stretch and Raspbian Buster
Create a file in this directory called wpa_supplicant.conf. The file should contain the following details:
```bash
network={
    ssid="YOUR_NETWORK_NAME"
    psk="YOUR_PASSWORD"
    key_mgmt=WPA-PSK
}	
```

### Connecting to unsecured networks
For wireless networks with no password, use the following:
```bash
country=US # Your 2-digit country code
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev # Include this line for Stretch
network={
    ssid="YOUR_NETWORK_NAME"
    key_mgmt=NONE
}	
```
With this file in place, Raspbian will move it in /etc/wpa_supplicant/ when the system is booted.

The next step is to boot the Pi and test, but while the SD card is still in your computer I'll mention this now. If you're going to try to connect via SSH, you may need to enable it first. The process is similar to this one.

## Step 4: Put your SD card in the Raspberry Pi, boot, and connect.

Next, put the micro SD card into the Pi, boot, and your Wi-Fi should be connected!

The wpa_supplicant.conf file should disappear from the SD card's boot directory automatically—so if you don't see it next time, that's normal.

## Step 5: Troubleshooting

If your Pi hasn't connected to Wi-Fi, try these wpa_supplicant troubleshooting tips:

1.Double-check that the file was written in plaintext, without any special characters.
2.Double-check that the file has disappeared from your boot directory.
3.Connect the Pi to a TV or monitor via HDMI to ensure it is booting normally.
4.If you're using a Raspberry Pi Zero W, make sure you're attempting to connect to a 2.4GHz network (the Zero doesn't support 5G).
5.If you're using a Raspberry Pi Zero, make sure it's a Raspberry Pi Zero W, not a regular Zero (only the W supports Wi-Fi and Bluetooth).

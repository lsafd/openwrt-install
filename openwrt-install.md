# OpenWrt Install

### Purpose:

This guide will explain how to install OpenWrt on a compatible router. This guide will only cover basic settings and a few other customization options.

### Prerequisites:

* [OpenWrt compatible router](https://openwrt.org/supported_devices)

* [OpenWrt firmware](https://openwrt.org/downloads)

* Ethernet connection to your router

### 0. Firmware Flashing:

Go to your router's control page by typing it's IP into your browser's search bar. (Most likely 192.168.1.1, 192.168.0.1 or 10.0.0.1)

Find the section of your router's control page where you can update the firmware.

Choose update from file and select the OpenWrt firmware file. (If it is not clear how to flash the firmware on your specific router check the [OpenWrt documentation](https://openwrt.org/docs/start) on the OpenWrt website)

Wait for the flashing to complete and reboot your router.

### 1. Initial Setup:

Connect to your router using ethernet. (You may be able to connect to a network called OpenWrt, but it is inconsistent.)

Go to your router's control page by typing it's IP into your browser's search bar. (Most likely 192.168.1.1, 192.168.0.1 or 10.0.0.1)

Follow the prompt that tells you your router does not have a password and set a password for your router.

Login with the password that you have created. (It may tell you that the page is insecure because it is http not https, but for now don't worry about it.)

### 2. Secure SSH Setup:

If you plan to SSH into your router in the future, as opposed to using the web GUI, you should open **System >> Administration >> SSH-Keys** and add your SSH public key.

From there, got to **SSH Access**, disable `Password authentication` and `Allow root logins with password`, and click `Save & Apply`.

### 3. Network Setup:

Open **Network >> Wireless**.

Under each WiFi radio there should be a network. Click `Edit`.

Under the **General Setup** tab, name your network.

Then, open the **Wireless Security** tab. For `Encryption` choose `WPA2-PSK` and type your WiFi password into the `Key` field.

To save you changes click `Save`.

You can repeat this process for any other radios that your router has. If you apply the same settings to multiple radios they will appear as one network.

You should now be able to connect to your network using WiFi.

### 4. Setting a Static IP:

Open **Network >> DHCP and DNS >> Static Leases**.

Click `Add`, identify the device and IP address that you want to assign, and click `Save`.

Click `Save & Apply` to save your changes.

### 5. Port Forwarding:

Open **Network >> Firewall >> Port Forwards**.

Click `Add`, identify the ports that you want to forward, and click `Save`.

Click `Save & Apply` to save your changes.

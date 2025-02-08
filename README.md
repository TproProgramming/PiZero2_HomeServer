# Raspberry Pi Zero 2 W Web Server Setup

This repository documents my process of setting up a home web server using the Raspberry Pi Zero 2 W. This is an educational project and my first time experimenting with webservers. 

## Prerequisites
- Raspberry Pi Zero 2 W
- MicroSD card (at least 8GB recommended)
- Power adapter
- Internet connection (Wi-Fi)
- Computer with Raspberry Pi Imager installed

## Setup Instructions
### 1. Flash Raspberry Pi OS
- Download **Raspberry Pi OS Lite (64-bit)**.
- Use **Raspberry Pi Imager** to flash the OS onto the microSD card.
- During setup, configure the following:
  - **Username and password** (Avoid using defaults for security).
  - **Wi-Fi credentials**.
  - **Enable SSH** for remote access.

### 2. Connect to the Raspberry Pi
- Insert the microSD card into the Raspberry Pi and power it on.
- SSH into the device using:
  ```sh
  ssh pi@raspberrypi.local
  ```
  - If this doesn't work, find the Pi's IP address using `arp -a` or check your router's device list.
  - Enter the password when prompted.

### 3. Update the System
- Run the following commands to update and upgrade the system:
  ```sh
  sudo apt update && sudo apt upgrade -y
  ```

### 4. Install Apache Web Server
- Install Apache using:
  ```sh
  sudo apt install apache2 -y
  ```
- Verify installation by visiting the Raspberry Pi's IP address in a web browser. You should see the default Apache webpage.

### 5. Modify the Default Webpage
- Navigate to the web root directory:
  ```sh
  cd /var/www/html
  ```
- Edit the default HTML file:
  ```sh
  sudo nano index.html
  ```
- Modify the content as needed, then save and exit (`CTRL + X`, then `Y` and `Enter`).
- Refresh your browser to see the changes.

### 6. Moving files using scp 
 - Make sure you have the correct permissions set.
 - Transfer files using secure copy
   ```sh
   scp example.txt pi@<IP ADDRESS>:/home/pi/
   ```

## Next Steps
- Set up **PHP** or **Python (Flask/Django)** for dynamic content.
- Configure **port forwarding** to access the server externally.
- Secure the server with **fail2ban** and **UFW firewall**.
- Automate updates and backups.

More updates coming soon!


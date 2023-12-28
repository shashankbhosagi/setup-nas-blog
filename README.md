# NAS

## What is a Nas ?!
NAS stands for Network Attached Storage. It's a type of dedicated file storage device that provides local-area network (LAN) nodes with file-based shared storage through a standard Ethernet connection. In simpler terms, a NAS device is like a specialized, high-capacity hard drive that is connected to your network and can be accessed by multiple devices.

Key features of a NAS include:

1. **File Sharing:** NAS devices allow multiple users and devices to share and access files over a network. This is useful for home and office environments where centralized file storage is needed.

2. **Data Redundancy and Backup:** Many NAS devices support RAID configurations, providing data redundancy to protect against drive failures. Some NAS devices also offer built-in backup features.

3. **Remote Access:** Users can often access the files on a NAS remotely, either through a web interface or dedicated apps, making it convenient for users who need to access their data from different locations.

4. **Media Streaming:** Some NAS devices come with media server capabilities, allowing users to stream multimedia content to connected devices like smart TVs, game consoles, or media players.

5. **Data Security:** NAS devices often come with security features such as user authentication, encryption, and access control, providing a secure environment for storing sensitive data.

6. **Expandable Storage:** NAS devices are scalable, allowing users to add more storage capacity as their needs grow. This is typically achieved by adding additional hard drives or upgrading existing ones.

Popular NAS manufacturers include Synology, QNAP, Western Digital, and Buffalo. NAS devices are commonly used in homes, small businesses, and offices to create a centralized and easily accessible storage solution.

## Minimum Hardware required

1. Raspberry Pi (any)
2. MicroSD Card (8GB or larger)
3. Power Supply (micro USB or suitable to your pi)
4. External Hard Drive or USB Storage
5. Ethernet Cable (optional)

## Steps

### Step 1. Setup SD card

![Flashing_process_NEWe](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/78fd0556-fe11-42a1-bf13-af3ea010df7e)


1. **Download Raspberry Pi Imager:**
   - Download the Raspberry Pi Imager from the official Raspberry Pi website: [Raspberry Pi Imager](https://www.raspberrypi.org/software/).

2. **Install Raspberry Pi Imager:**
   - Run the installer and follow the on-screen instructions to install the Raspberry Pi Imager on your computer.

3. **Insert MicroSD Card:**
   - Insert the MicroSD card into your computer using a MicroSD card reader.

4. **Launch Raspberry Pi Imager:**
   - Open the Raspberry Pi Imager software on your computer.

5. **Select Operating System:**
   - Click on "Choose OS" and select the operating system you want to install. For a NAS setup, you might choose "Raspberry Pi OS (other)" or "Raspberry Pi OS Lite" for a minimal installation.

6. **Select SD Card:**
   - Click on "Choose SD Card" and select the MicroSD card you inserted.

7. **Configure Options:**
   - Click on "Options" at the bottom right corner of the Raspberry Pi Imager.

8. **Configure Wi-Fi:**
   - In the "Options" menu, you'll find a section for Wi-Fi.
   - Enter your Wi-Fi SSID and password.

9. **Configure Hostname:**
   - In the same "Options" menu, you can also set the hostname directly.

10. **Set Locale and Timezone (Optional):**
    - Adjust the locale and timezone settings if needed.

11. **Write the Image:**
    - Click on "Write" to start the process. This will write the selected operating system to the MicroSD card. Note that this will erase all data on the card.

12. **Wait for Completion:**
    - Wait for the write process to complete. This may take a few minutes.

13. **Eject MicroSD Card:**
    - Once the write process is complete, safely eject the MicroSD card from your computer.

14. **Insert MicroSD Card into Raspberry Pi:**
    - Insert the MicroSD card into the Raspberry Pi.

![Putting_in_the_Micro_SD_card](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/852d58ae-4aab-4574-9aa1-326d33aa4da0)



### Plugin your HardDrive or Pendrive































































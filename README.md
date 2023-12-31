# NAS

Tip : first do installation while connected to wifi then after installation use ethernet, I just faced a problem :). I installed on ethernet connected but after installation it was not connecting...

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

Note : While installing raspbeery pi os install 64-bit if possible because, it may affect the further application you install ;).

![Putting_in_the_Micro_SD_card](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/852d58ae-4aab-4574-9aa1-326d33aa4da0)



### Step 2. Plugin your HardDrive or Pendrive
 
1. **Connect the Hard Drive or Pendrive:**
   - Plug in your hard drive or pendrive into an available USB port on your computer.

2. **Open File Explorer:**
   - Open File Explorer to view your connected drives.

3. **Identify the Drive:**
   - Identify the drive letter assigned to your hard drive or pendrive. It will be listed under "This PC" or "Computer."

4. **Right-Click on the Drive:**
   - Right-click on the drive you want to format.

5. **Select "Format":**
   - From the context menu, select "Format."

6. **Choose File System:**
   - In the Format window, under "File system," select "NTFS."

7. **Allocation Unit Size (Optional):**
   - You can choose the allocation unit size. The default setting is usually fine, but you can adjust it based on your preferences.

8. **Volume Label (Optional):**
   - You can provide a name for your drive in the "Volume label" field. This is optional.

9. **Quick Format (Optional):**
   - If you want to perform a quick format, check the "Quick Format" option. This will erase the data quickly but is less thorough than a full format.

10. **Start the Format:**
    - Click on the "Start" button to begin the formatting process.

11. **Confirm Warning:**
    - Confirm any warning prompts that appear, indicating that all data on the drive will be deleted.

12. **Wait for Completion:**
    - Wait for the formatting process to complete. This may take a few minutes.

13. **Format Complete:**
    - Once the format is complete, you will see a confirmation message.

14. **Close the Format Window:**
    - Close the Format window.

      
![Format_that_USB_Right_and_good_Complete](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/7a133c99-4e73-4dbe-96a4-7039710bc4ed)


### Step 3. Connecting all hardware 

In this step connect raspbeery pi to power supply and also connect to hardrive to pi.
Now wait for 2 minutes so that PI will bootup...

### Step 4. Connect PI via SSH

GO to your router configuration in web ( I am using TP-Link Wireless N Router WR840N ). For configuration go to http://192.168.0.1/ and enter the credentials, after that you must see this page.

![Group 1](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/7fc7fb3c-ec94-42c9-b774-7f5853daf003)

GO to DHCP settings

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/b728da64-7991-4feb-aad9-ffe6eb524b8c)

Then under DHCP there is an option DHCP client list 

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/ae86e61d-aee3-4020-887d-7d97f0db826e)

You will find you private ip address for the raspbeery pi here mine is venom yours maybe pi or whatever you setup..

![Group 2](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/bdd05aac-6227-4062-a978-f57631dca74b)


After getting the private IP address go to command prompt or powershell make sure you have SSH installed on your computer.

TO connect to your pi enter this command 

```bash
ssh your-pi-name@pi's-private-ip-address
```

In my case 

```bash
ssh venom@192.168.0.105
```
See image below

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/cfdb7204-a3e8-4d63-a6c1-acfac29c62e6)

After this you will prompted for fingerprinting type yes then enter the password which you put during setup
after login it must look like this

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/981d7141-a3ec-4450-922d-af5c525c7b88)


then run these commands
```bash
sudo apt update
```

```bash
sudo apt upgrade -y
```

 Congratualtions now your are connected to your PI!!! 🥳🥳🥳


### Step 4. Installing Openmedia Vault on you PI 

After upgrade paste this command which will start the installation process
```bash
sudo wget -O - https://coreelec.io/openmediavault  | sudo bash
```

### `Note : It will take time, better you be prepared with some entertaiment stuff 😂👾, I am gonna watch One Piece :)`

Okay now it will restart bois and girls after the installation.

### `Note : If you are connected to a wifi network wireless then after reboot it won't connect wirelessly, so plug in the RJ45 in pi and connect it via Ethernet :)@@`

### Step 5. Configure OpenMediaVault

As we know our raspbeery pi's address its 192.168.0.105, now we will go to browser and type in searchbar `192.168.0.105` and hit enter

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/61a16a8d-b93f-4d26-8837-c905635bbad2)


it should look something like this 

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/f08226f3-0880-4590-80ab-b0418e0550da)

put default credentials as 
username : `admin`
password : `openmediavault`

after login it must look like this,

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/7ac679b9-2a9a-45fd-b01b-ee42606cafac)

go to user setting and click on change password

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/2d2fde2b-b271-4b07-a438-3dc81c3e0346)

put new and secure password and then click change password..

next step is to go to user section in left and onfigure new user which we will access from our computer 

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/4da4564d-0509-4c9d-b406-c35292f5fa48)

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/f0b0c551-7b94-402c-85d3-daf25d461f20)

click on save after entering the details 

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/c93d70ed-7ecb-419a-9621-0a1457ae45b6)

Now one more thing whenever you make any changes a yellow bar will pop-up on the top so please after making changes please ensure that you hit tick mark 

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/318314b8-e79f-4f55-937c-0cbd8d132e8b)

Next go to Storage section in left hand side navbar, go to `Filesystem`

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/c1471430-730d-40a8-9612-5c3ae2afce47)

after this click on play button which says mount an existing file system and then select the drive

![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/7b020bf4-9e95-471e-8b7e-f22b830bf92f)

Click on shared folders and create a folder which you will access from the PC
After this click on the created folder and give it read/write previlages 

Next step go under Services section and then click on SMB/CIFS then enable it for file transfer between your computer and raspbeery pi

Now under SMB/CIFS there would be new option called shares 
![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/23f50f27-7615-4a46-b751-7ab857213e9e)

and create a new share and add the shared folder and save it...

Note : Don't forget to click on tick mark in the yellow box to change the configuration settings

Hurray 🎉🎊 now we have setup our NAS which can be connected from any computer in local network. 




## Demonstration 

### GO to file explorer 
![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/ff46b55f-eae7-4daf-83a2-bd08d7dec636)
### Click on networks in left sidebar
![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/087c08f0-a06d-415a-b23d-0ba993a8d4a9)
### Click on venom
FIll the credentials and viola you will have access to the shared folder.
![image](https://github.com/shashankbhosagi/setup-nas-blog/assets/78866224/c5588881-4fc4-4c7d-90cd-bff3152d8281)

## Enjoy 
### You can create, delete, upload, download to the NAS 🎉

## Update
### Further what I did was connect my NAS to cloudflare using tunnel. And now I can access my NAS from anywhere in the world ;)... 


## Credits 

1) `Youtube Video` - https://youtu.be/zISwEoywvX4?si=agnCEETHVDnUO7Ee  : This was the video I reffered go and check them out it's amazing channel.
2) `Blog` - https://core-electronics.com.au/guides/raspberry-pi/how-to-raspberry-pi-nas/    : I also refered this for some images to explain what I was telling.





















































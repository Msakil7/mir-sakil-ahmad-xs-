

crypt0b0y
/
BLUETOOTH-DOS-ATTACK-SCRIPT
Public
Code
Pull requests
Actions
Projects
Security
Insights
BLUETOOTH-DOS-ATTACK-SCRIPT/README.md
@jieggii
jieggii Update README.md
 1 contributor
70 lines (57 sloc)  3.41 KB
Bluetooth DOS-Attack Script


Script for quick and easy DOS-attacks on bluetooth devices for pentest purposes

screenshot

Disclaimer
This project was created only for good purposes and personal use.

THIS SOFTWARE IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY KIND. YOU MAY USE THIS SOFTWARE AT YOUR OWN RISK. THE USE IS COMPLETE RESPONSIBILITY OF THE END-USER. THE DEVELOPERS ASSUME NO LIABILITY AND ARE NOT RESPONSIBLE FOR ANY MISUSE OR DAMAGE CAUSED BY THIS PROGRAM.

Installing
$ sudo apt update
$ sudo apt install python3
$ sudo git clone https://github.com/mirsakil/BLUETOOTH-DOS-ATTACK-SCRIPT.git
$ cd BLUETOOTH-DOS-ATTACK-SCRIPT/
$ python3 Bluetooth-DOS-Attack.py
Note
The script works only with Linux systems.

You must have "l2ping" util on your linux machine (it installed as default on Kali Linux).

YOU MUST SCAN AND ATTACK BEFORE SOMEONE CONNECT TO THE TARGET!!!

It tested on
Kali Linux as attacker, and Xiaomi Portable Bluetooth Speaker as target

Using
First of all, you must scan network for Bluetooth devises. For example, you can use "hcitool".

$ sudo apt update
$ apt install hcitool
$ sudo service bluetooth start
$ hcitool scan
Output will be like:

A1:B2:C3:D6:E7      Xiaomi portable speaker
B1:C2:D3:E4:F5      iPhone(Toivo)
C1:D2:E3:F4:G5      Some Bluetooth device
Then copy target addres (for example "A1:B2:C3:D6:E7") and paste it in "Target addr".

Manual
"Target addr" - addres of your target (Check info above).
"Packages size" - size of the packages, that will be sent to the target. 600 is optimal.
"Threads count" - number of threads, that will send packages to the target at the same time. I used 500 threads, and that was enough. Check the table below, to find optimal value.
Packages size	Threads count	Ping, ms	Distance, meters	Time waited, sec	Device
600	1	9	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	10	38	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	20	78	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	50	229	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	100	413	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	200	806	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	500	1961	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	1000	6621	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
600	1000+	Couldn't calculate	0,3	5	Xiaomi Mi Portable Bluetooth Speaker
What happens to the target device
I can't say about all devices, but device I tested just turned off.

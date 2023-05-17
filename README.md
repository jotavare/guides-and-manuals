# Wi-Fi Network Hacking Guide (Educational)

When you enable Wi-Fi in public places, you'll encounter numerous networks that likely utilize WPA-PSK encryption. Although these networks are susceptible to hacking, it is crucial to emphasize that this guide is strictly for educational purposes. Engaging in these activities on networks without proper authorization is illegal. Having addressed this disclaimer, let's explore the underlying mechanisms, the practical execution, and measures to safeguard yourself against such vulnerabilities.

## Introduction

When you connect to a network from a wireless device, a handshake is sent from the device to the router. This handshake contains the encrypted password. While it's not possible to reverse the encrypted password, you can use a technique called a word list attack. A word list is a huge text file containing thousands of passwords. By comparing the encrypted handshake password with the passwords in the word list, you can determine the real password.

## Requirements

To perform Wi-Fi network hacking, you'll need a computer running Linux. In this guide, we'll use Kali Linux as it comes with the necessary tools pre-installed. If you're using another Linux distribution, you'll need to download the required packages. Additionally, if your computer's network card doesn't support monitor mode, you'll require an external network card such as the TP-Link adapter mentioned below.

## Procedure

Determine the Network Interface: Open a terminal and type ip a. Identify the wireless network interfaces, which usually start with wlanX (e.g., wlan0). This information will be needed later.

Enable Monitor Mode: Use the airmon-ng tool to switch your network card to monitor mode. Enter the command airmon-ng start <wireless interface>, replacing <wireless interface> with the name of your wireless interface (e.g., wlan0). This command will enable monitor mode on your network card, but it will break your internet connection temporarily.

Verify Monitor Mode: Run the command iwconfig in a terminal to check if the network card's mode has changed to monitor. The wireless interface should be displayed as <interface>mon (e.g., wlan0mon). If not, it means your network card doesn't support monitor mode, and you'll need the external network card mentioned earlier.

Scan for Networks: Use airodump-ng to view the networks around you. Enter the command airodump-ng <wireless interface>mon (e.g., airodump-ng wlan0mon). This command will display a list of nearby networks along with their BSSIDs (network MAC addresses) and channels.

    Target Network: Identify the BSSID and channel of the network you wish to attack.

    Capture the Handshake: In a new terminal window, enter the command airodump-ng --bssid <BSSID> --channel <channel> --write <filename> <wireless interface>mon. Replace <BSSID> with the target network's BSSID, <channel> with the target network's channel, <filename> with the desired name for the captured handshake file, and <wireless interface>mon with the name of your wireless interface in monitor mode. This command will start capturing the handshake from devices connected to the target network.

    Deauthentication Attack: To force a device to reconnect and capture the handshake, use the command aireplay-ng -0 10 -a <BSSID> -c <client ESSID> <wireless interface>mon. Replace <BSSID> with the target network's BSSID, <client ESSID> with the ESSID (name) of the device you want to deauthenticate (e.g., the victim's device), and <wireless interface>mon with the name of your wireless interface in monitor mode. This command will send deauthentication packets to the victim's device, forcing it to disconnect and reconnect to the network.

    Capture the Handshake: Observe the terminal running airodump-ng and wait for a device to reconnect. Once the handshake is captured, you can stop airodump-ng by pressing Ctrl+C. The captured handshake will be saved in the specified filename.

    Word List Attack: Kali Linux comes with pre-installed word lists located in the directory mentioned below. Use the aircrack-ng command to crack the password. Enter aircrack-ng -w <wordlist> <filename> to start the cracking process. Replace <wordlist> with the path to the desired word list file (e.g., /usr/share/wordlists/rockyou.txt), and <filename> with the name of the captured handshake file. This command will attempt to match the captured handshake with passwords from the word list.

    Protecting Yourself: While you cannot prevent the authentication process, you can protect against word list attacks by choosing a long and random password that is unlikely to be found in any word list.

---
  
Note: After performing these steps, your internet connection may still be interrupted. To fix this, you can either restart your computer or execute the command airmon-ng stop <monitor interface> followed by systemctl restart network* to restart the network services.
Conclusion

In this guide, we explored the process of Wi-Fi network hacking for educational purposes only. It is essential to respect privacy and legality when using these techniques. We discussed capturing handshakes, performing deauthentication attacks, and cracking passwords using word lists. Remember to always use this knowledge responsibly and protect yourself by setting strong passwords for your Wi-Fi networks.

If you found this guide helpful, feel free to leave a like and thank you for reading!

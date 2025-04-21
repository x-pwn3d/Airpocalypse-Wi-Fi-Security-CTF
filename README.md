# 🔓 Airpocalypse – Wi-Fi Security CTF

**Airpocalypse** is a custom Capture The Flag (CTF) challenge designed to raise awareness around wireless network security and the real-world exploitation of WEP and WPA/WPA2 vulnerabilities. Built around **Aircrack-ng**, this CTF offers a practical deep dive into how poorly secured Wi-Fi networks can be compromised through packet analysis, injection, and brute-force attacks.

> ⚠️ **Note**: This CTF was designed as a **physical event** with a tightly controlled scenario that requires proximity to a configured router. As such, the challenge itself cannot be distributed publicly. However, walkthrough **videos** demonstrating both the WEP and WPA2 scenarios are provided to showcase the attack process.

---

## 🧪 Challenge overview

### 🔐 WEP Challenge – Fragmentation attack & IV collection

The goal of this scenario is to **capture a maximum number of Initialization Vectors (IVs)** to break the WEP key.

Steps involved:

1. Switch your interface to monitor mode and capture Wi-Fi traffic.
2. Launch a **fragmentation attack** to recover a keystream.
3. Forge an **ARP packet** using the captured keystream.
4. **Inject the forged packet** to stimulate traffic on the network.
5. Capture enough IVs and crack the WEP key using **aircrack-ng**.

---

### 🔐 WPA2 Challenge – Handshake capture & Brute-Force

This challenge focuses on capturing a WPA2 handshake and brute-forcing the password.

Steps involved:

1. Put your card into monitor mode and scan for nearby APs.
2. Perform a **deauthentication attack** on a connected client.
3. Capture the **WPA2 4-way handshake** using `airodump-ng`.
4. Use **dictionary-based brute-force** with `aircrack-ng` to recover the key.

#### 🔧 Bonus Stage – PHP Vulnerability (hash_hmac)

An additional web challenge was integrated into the scenario. After recovering the WPA2 password, participants could access a local web service vulnerable to an insecure implementation of `hash_hmac()`, allowing for a simple bypass and flag extraction.

---
## 🖥️ Hardware used

This CTF was tested and performed using the following Wi-Fi adapters:

- 🧩 **Alfa Network AWUS036ACS** – 802.11ac, compact, reliable for basic injections  
- 🧩 **Alfa Network AWUS036ACH** – 802.11ac dual-band, supports monitor mode and high-power packet injection  

These adapters are known for their compatibility with Kali Linux and excellent performance in wireless security testing environments.
---

## 🎥 Walkthrough videos

While the full scenario cannot be shared due to its physical setup, the following walkthroughs are available:

- 📼 [**WEP Attack Walkthrough**](https://youtu.be/_L5e0vU42ic) 
- 📼 [**WPA2 Attack Walkthrough + Bonus PHP Exploit**](https://youtu.be/G_v3nTH42cU)

> Videos demonstrate the full attack chain in a lab environment replicating the competition setup.

---

## 📎 Requirements

- A compatible **Wi-Fi adapter** supporting monitor mode and packet injection
- Kali Linux or any distro with the **Aircrack-ng suite**
- Wordlists for WPA2 dictionary attack (e.g., `rockyou.txt`)

---

## 📬 Feedback

If you found the walkthroughs helpful or have questions about the setup, feel free to open an issue or reach out. This repo aims to help others understand wireless vulnerabilities and practice responsibly.

---
## ⚠️ Legal notice

This project is intended for **educational purposes only**. All demonstrations were conducted in an isolated, authorized lab environment.  
**Never attempt to target Wi-Fi networks without explicit permission.**


**Stay safe, stay curious, and hack the airwaves! 🚀**


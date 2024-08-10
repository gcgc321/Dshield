# DShield Honeypot Project

## Introduction

The **DShield Honeypot Project** is designed to collect and report data on malicious network activity. This honeypot setup is lightweight and easy to deploy, allowing users to contribute valuable data to the SANS Institute's DShield network.

![rsz_honeypot_deployment-scheme](https://github.com/user-attachments/assets/db04b0a8-a244-46a1-b61d-9da4a6b91b64)



## Abstract 

By collecting data through this honeypot, we can analyze how attackers exploit poorly configured ports.

## Skills
- **Networking**
- **Linux**
- **Cybersecurity Threat Intelligence**
- **Cloud Deployments**

## Features

- **Easy Setup**: Simple configuration and deployment process.
- **Data Collection**: Captures network traffic data and reports it to DShield.
- **Modular Design**: Extensible and customizable to suit various deployment scenarios.

## Prerequisites

- **Operating System**: Linux-based system (e.g., Debian, Ubuntu).
- **Devices**: Raspberry Pi or Cloud VM.

## Installation for Proof of Concept

### Step 1: Set Up Raspberry Pi 5 with Your Linux Distro

1. Prepare a microSD card using a computer with the Raspberry Pi Imager installed.
2. Insert the configured microSD into your Raspberry Pi and power it on.

### Step 2: SSH into the Pi and Execute the Following Commands

![raspberrypi ssh](https://github.com/user-attachments/assets/fc239067-8b62-4880-8b56-8d872e799eba)


1. **Update and Upgrade and Install Git:**
  
 ![Update rpi with commands](https://github.com/user-attachments/assets/6a1febb3-2087-4f13-9310-4c51bd3dde3f)


2. **Clone the DShield repository:**

   ![Installing dshield](https://github.com/user-attachments/assets/f034e3db-0940-4f20-a75a-490a3642a59e)


3. -**Install Dshield**

  ![run dhsield installation script](https://github.com/user-attachments/assets/cb98e8f8-bed4-4411-a890-ef0c8743618d)

  

4. **Configure the Settings as Needed.**
 
![Warning Honeypi](https://github.com/user-attachments/assets/33d042e7-f0c1-43d9-b22d-8c746d2a3f7d)

5. **Obtain Your API Key from the SANS Website by Creating a Login.**
https://isc.sans.edu/tools/honeypot/index.html

6. **Access the Logs of DShield via the Website.**

   

### Step 3: Testing and Deployment

- To test the honeypot, use an instance of Kali Linux in a VirtualBox VM:
  - Perform an Nmap scan to identify open ports.
    
   ![open ports 1](https://github.com/user-attachments/assets/36e4701e-b795-4cc8-a028-ded3f6913f31)

  - Use Metasploit to brute-force login credentials over port 23.
    
    ![metasploit brute forcing telnet 23](https://github.com/user-attachments/assets/e3e599a6-1035-40d6-95a9-ec0d7aa4410b)

    ![metasploit attempts](https://github.com/user-attachments/assets/75b96a77-29e8-4399-9039-b0e59f5c1c35)

  - Logs will update every 30 minutes, reflecting detected activity.
 
    

    

### Step 4: Deploy to the Public Internet

- Techincally you can stop here and then use the raspberry pi. Place it on your network's DMZ or allow port forwarding to expose it to the world wide web.
- I went with a cloud provider to mitigate the risk of an attacker pivoting to my SoHo network. 
- Choose a cloud provider (e.g., Vultr) and set up an instance of 64-bit Linux 22.04 LTS.
- Follow the same installation steps as with the Raspberry Pi.
- Tweak your firewall rules to allow TCP/UDP traffic from ports 1-65535.
- Monitor the collected data to observe malicious activity targeting your honeypot.
- Within 24 hours of this honeypot being provisioned it was hit by 38 unique IPs from across the world mainly Asia and Russia.
- On ports 22(SSH) and 23(Telnet) they tried to bruteforce in with a total of 921 guesses. 
<img width="1680" alt="Screenshot 2024-08-09 at 8 08 58 PM" src="https://github.com/user-attachments/assets/ef4b6bde-a87a-425f-bced-dee7c708b133">

<img width="1680" alt="Screenshot 2024-08-09 at 8 50 16 PM" src="https://github.com/user-attachments/assets/39a4bc0d-7369-419d-bfb2-fec846f44cb8">



## Conclusion

The logs clearly demonstrate that IP addresses from around the world are actively scanning and attempting brute-force attacks on the honeypot. The usernames and passwords used in these attacks are typically
basic, often reflecting default credentials. This highlights the critical importance of creating strong, complex passwords to prevent unauthorized access to sensitive data. For detailed guidance on password
requirements, NIST 800-63b is an excellent resource. I encourage you to replicate this experiment and consider contributing to the DShield network, where you can gain valuable insights into real-world attack
patterns and help strengthen cybersecurity defenses.





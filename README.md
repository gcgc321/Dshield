# DShield Honeypot Project

## Introduction

The **DShield Honeypot Project** is designed to collect and report data on malicious network activity. This honeypot setup is lightweight and easy to deploy, allowing users to contribute valuable data to the SANS Institute's DShield network.

## Abstract 

By collecting data through this honeypot, we can analyze how attackers exploit poorly configured attack surfaces.

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

1. **Install Git:**
  
   
2. **Clone the DShield repository:**

 


3. -**Install Dshield**

  
  

4. **Configure the Settings as Needed.**

5. **Obtain Your API Key from the SANS Website by Creating a Login.**

6. **Access the Logs of DShield via the Website.**

7. **Use Port 12222 as Your Admin Console Port.**

### Step 3: Testing and Deployment

- To test the honeypot, use an instance of Kali Linux in a VirtualBox VM:
  - Perform an Nmap scan to identify open ports.
  - Use Metasploit to brute-force login credentials over port 23.
  - Logs will update every 30 minutes, reflecting detected activity.

### Step 4: Deploy to the Public Internet

- Choose a cloud provider (e.g., Vultr) and set up an instance of 64-bit Linux 22.04 LTS.
- Follow the same installation steps as with the Raspberry Pi.
- Tweak your firewall rules to allow TCP/UDP traffic from ports 1-65535.
- Monitor the collected data to observe malicious activity targeting your honeypot.

## Conclusion

The logs clearly demonstrate that IP addresses from around the world are actively scanning and attempting brute-force attacks on the honeypot. The usernames and passwords used in these attacks are typically
basic, often reflecting default credentials. This highlights the critical importance of creating strong, complex passwords to prevent unauthorized access to sensitive data. For detailed guidance on password
requirements, NIST 800-63b is an excellent resource. I encourage you to replicate this experiment and consider contributing to the DShield network, where you can gain valuable insights into real-world attack
patterns and help strengthen cybersecurity defenses.





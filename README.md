# Protocol_Detection_Tool

Using a variety of modules, a flexible Python network management tool to analyze network security and network protocols. It checks that TLS and IPsec are present in the network infrastructure and looks at BGP capability. Additionally, the tool evaluates the data link layer resilience of the network by simulating an ARP spoofing attack. It is crucial to remember that this tool should only be used for educational purposes and should never be used maliciously.

This README provides instructions on how to run the Detector code.

## Table of Contents

 [Protocol_Detection_Tool](#Protocol_Detection_Tool)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Installation Steps](#installation-steps)
  - [Running the code](#running-the-code)
  - [Description](#description)
    - [IPsec](#ipsec)
    - [TLS](#tls)
    - [ARP Spoof Attack](#arp-spoof-attack)
    - [BGP Analysis](#bgp-analysis)
  - [Limitations](#limitations) 


## Installation

### Prerequisites

1. This tool is meant for Debian linux distros like Kali. It can also run on Ubuntu. It doesn't run on Windows.

Before installing Scapy, make sure you have the following prerequisites:

2. **Python**: Scapy requires Python 3.x. Make sure you have Python installed on your system. From your terminal, run `sudo apt update` then `sudo apt install python3 python3-pip libpcap-dev` to install both python3 and pip3. Check the official website for more information: [Python Downloads](https://www.python.org/downloads/).

### Installation Steps

1. From your terminal, install all libraries using pip by running the following command: `pip install -r requirements.txt`. This will download and install all the requirements.


2. Once the installation is complete, you can clone our code using the command:
```
git clone https://github.com/HadiElNawfal/Protocol_Detection_Tool
```
## Running the code

Run `python ProtocolDetector.py -h` to see the help page.

## Description

This code can test for:

### IPsec
* Function to make sure packets are sent from the device using IPsec protocol
* Validates IP header
* Checks for protocol number
* Protocol number 50 for IPsec ESP
* Protocol number 51 for IPsec AH
* Protocol number 6 for TCP
* Protocol number 17 for UDP
### TLS
* Function to check if packets sent from the device are using TLS protocol
* Takes a URL as input and validates the website URL format
* Checks for HTTPS support
* Checks for HSTS (HTTPS Strict-Transport-Security) in https header
* Create a custom SSL context to get SSL/TLS information
* Prints specifications of TLS used
### ARP Spoof Attack
* Function to simulate a arp-spoof man in the middle attack to check if the network is vulnerable
* Utilize Scapy's ping function to discover devices on the network
* Get the MAC and IP address of the gateway with the help of get_gateway_mac_address function
* Maintain internet connection on the target through IP forwarding
* Update the ARP tables
* Send a fake packet saying that we're at the router's IP to the target machine
* Send a packet to the router that we are at the target machine's IP
* Sniff packets on the network and writes it to a pcap file
### BGP Analysis
* Function to check the safety of the BGP used
* Obtain ISP name
* Utilize "Is BGP Safe Yet?" to check if ISP is safe
* Initialize a stream using PyBGPStream
* Extract specific details of the ISP such as time-stamp, routes, origin and many more
* Analyze the BGP of the ISP

## Limitations
1. Basic Detection:
Detects only ESP (protocol 50) and AH (protocol 51) by protocol number. It cannot verify payload encryption or decryption success.
2. No Logging:
Outputs are printed to the terminal only, and no persistent logs are generated for later analysis or forensic use.
3. No Modular Design:
The script mixes multiple tools (TLS check, IPsec sniffing, ARP spoofing, BGP analysis) into a monolithic file

All cases and a tutorial are shown in the **Demo** video.





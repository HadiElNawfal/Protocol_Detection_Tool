# Protocol_Detection_Tool


This README provides instructions on how to run the Detector code.

## Table of Contents

 [Protocol_Detection_Tool](#Protocol_Detection_Tool)
  - [Table of Contents](#table-of-contents)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Installation Steps](#installation-steps)
  - [Running the code](#running-the-code)


## Installation

### Prerequisites

1. This tool is meant for Debian linux distros like Kali. It can also run on Ubuntu. It doesn't run on Windows.

Before installing Scapy, make sure you have the following prerequisites:

2. **Python**: Scapy requires Python 3.x. Make sure you have Python installed on your system. From your terminal, run `sudo apt update` then `sudo apt install python3 python3-pip libpcap-dev` to install both python3 and pip3. Check the official website for more information: [Python Downloads](https://www.python.org/downloads/).

### Installation Steps

1. From your terminal, install Scapy using pip by running the following command: `pip3 install scapy`. This will download and install Scapy and its dependencies.


2. Once the installation is complete, you can clone our code using the command: git clone https://github.com/HadiElNawfal/Protocol_Detection_Tool

## Running the code

Run `python ProtocolDetector.py -h` to see the help page

This code can test for:

IP or IPSec

All cases and a tutorial are shown in the **Demo** video.





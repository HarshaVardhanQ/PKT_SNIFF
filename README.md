# Network Packet Capture and URL Detection with Npcap

This project captures network packets and extracts HTTP/HTTPS URLs from TCP packets using Npcap and C++.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [Npcap](#npcap)
  - [Visual Studio Setup](#visual-studio-setup)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Contributing](#contributing)
- [License](#license)

## Overview

This program uses **Npcap** to capture network packets on a selected network interface, filters for TCP traffic, and detects HTTP/HTTPS URLs from the captured packets. The program works by parsing the packet payload for URL patterns and prints detected URLs in real time. The capture loop can be interrupted with `Ctrl+C`, which triggers a graceful exit.

## Features
- Lists available network interfaces using Npcap.
- Captures live network packets (TCP only).
- Detects HTTP/HTTPS URLs in the packet payload.
- Graceful shutdown with signal handling (`Ctrl+C`).
- Debug output for packet details.

## Prerequisites

To run this project, you need the following:
1. **Npcap** - A packet capture library for Windows.
2. **Visual Studio** - The IDE used for compiling and running the project.
3. **C++ Standard Libraries** - Required for string manipulation, regular expressions, and signal handling.

### Npcap
Npcap is an open-source packet capture library for Windows, a modern version of WinPcap.

- **Download Npcap**: You can download Npcap from [here](https://nmap.org/npcap/).
- **Installation**: Follow the installation instructions on the Npcap website. Ensure that you select the option to install the Npcap SDK, as it is necessary for compiling the code.

### Visual Studio Setup

1. **Download Visual Studio**: Install Visual Studio 2022 (Community edition is free) from [here](https://visualstudio.microsoft.com/downloads/).
   
2. **Install C++ Development Tools**:
   - During installation, ensure you select the "Desktop development with C++" workload.
   - Additionally, make sure to install the **Windows SDK** and **Npcap SDK** to integrate with the project.

3. **Set Up Your Project**:
   - Create a new **Console Application** in Visual Studio.
   - Add the **Npcap** include and lib directories to the project settings:
     - Go to **Project > Properties > VC++ Directories**.
     - Add the Npcap include directory (`C:\Program Files\Npcap\Include`) to **Include Directories**.
     - Add the Npcap lib directory (`C:\Program Files\Npcap\Lib`) to **Library Directories**.
   - Add the **npcap** library to the project:
     - Go to **Project > Properties > Linker > Input**.
     - Add `wpcap.lib` and `Packet.lib` to **Additional Dependencies**.

## Installation

1. **Install Npcap**:
   - Download and install Npcap from the official website. Make sure to include the SDK during the installation.
   - After installation, restart your computer if necessary.

2. **Install Visual Studio 2022**:
   - Download Visual Studio from the official website and follow the installation instructions.
   - Ensure the **C++ Desktop Development** workload is selected during installation.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/HarshaVardhanQ/PKT_SNIFF.git
   cd NetworkPacketCapture

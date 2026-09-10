# HAT-Lab Artifact Guide

## Overview

HAT-Lab is the platform designed for conducting User Studies. It allows for one-click deployment and usage.

## Prerequisites

- You must have **Docker** installed on your system.
- An **OpenAI API key** to run the application.

### System Requirements

The platform can run on any computer with Docker installed (e.g., WSL, Ubuntu, or macOS), but a powerful server with high CPU and memory capacity is recommended to ensure smooth operation. Below are the minimum and recommended configurations:

- **Minimum Configuration**: 
  - CPU: 4 cores
  - Memory: 8 GB RAM
  - Storage: 50 GB free disk space

- **Recommended Configuration**:
  - CPU: Multi-core processor
  - Memory: 64 GB RAM or higher
  - Storage: 500 GB SSD or higher

## Running the Application

1. **Download the Docker Image** (`hat-lab.tar.gz`)

2. **Load the Docker Image**

   ```shell
   gunzip hat-lab.tar.gz
   docker load -i hat-lab.tar
   ```

3. **Run the Application**

   Execute the following command with your OpenAI API key:

   ```shell
   docker run --rm -p 7860:7860 -e OPENAI_API_KEY="sk-..." hat-lab:latest
   ```

4. **Access the Web Interface**

   Open your browser and go to [localhost:7860](localhost:7860)

## Server Configuration (For Reference)

Below is the configuration of the server used to deploy HAT-Lab during our study:

```
=== System Configuration Report ===
Generated: Sat Aug 16 10:37:45 AM

=== Operating System Information ===
PRETTY_NAME="Ubuntu 22.04.5 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.5 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
Kernel Version: 5.15.0-131-generic
Architecture: x86_64

=== CPU Information ===
AMD EPYC 7763 64-Core Processor
CPU Cores: 256
Physical CPUs: 2
Cores per CPU: 64

=== Memory Information ===
               total        used        free      shared  buff/cache   available
Mem:           2.0Ti       121Gi       121Gi       109Mi       1.7Ti       1.8Ti
Swap:          8.0Gi       8.0Gi       0.0Ki
Total Memory: 2101198500kB

=== Storage Information ===
Disk Usage:
Filesystem                     Size  Used Avail Use% Mounted on
/dev/nvme0n1p2                 879G  826G  8.6G  99% /
/dev/nvme1n1                   880G  677G  158G  82% /home1
/dev/nvme0n1p1                 511M  6.1M  505M   2% /boot/efi
/dev/nvme2n1                   3.5T  3.2T   82G  98% /home2

Disk Devices:
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
nvme0n1     259:0    0 894.3G  0 disk 
nvme1n1     259:3    0 894.3G  0 disk /home1
nvme2n1     259:4    0   3.5T  0 disk /home2

=== GPU Information ===
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08
NVIDIA A100-SXM4-80GB, 81920, 550.127.08

=== Installed Key Software Versions ===
Python 3.13.2
Docker version 27.5.1, build 9f9e405
git version 2.34.1
gcc (Ubuntu 11.4.0-1ubuntu1~22.04) 11.4.0
```

## Notes

- The application will automatically configure itself with the provided API keys.
- All data is ephemeral and will be lost when the container stops.
- No additional setup or configuration is required.
- The web frontend is adapted from the open-source project [ChuanhuChatGPT](https://github.com/GaiZhenbiao/ChuanhuChatGPT), thanks to their contribution. This project is independent and not affiliated with the original authors.
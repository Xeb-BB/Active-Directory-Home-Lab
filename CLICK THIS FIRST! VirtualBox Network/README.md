# Lab Module: VirtualBox Private Network Configuration
## Before Everything Else
### Before deploying Active Directory services, it is important to first understand and configure the foundation of network communication inside a virtual environment. This lab focuses on building a simple private network between a Windows Server and Windows Client using VirtualBox.

### The goal of this project is to strengthen my hands-on skills in virtualization, networking, troubleshooting, and Windows Server administration through real-world lab practice and documentation.

## Tools & Technologies Used
### Oracle VirtualBox
### Windows Server 2022
### Windows 10 Pro
### TCP/IP Networking
### Internal Network Configuration
### Virtual Machine Administration
## What to Expect in this Repository
###  Procedure Checklist
###  Network Flowchart
###  Virtual Network Topology

# Virtual Network Topology
## This topology represents the foundation of my Active Directory home lab environment built using Oracle VirtualBox. The setup consists of a Windows Server 2022 virtual machine and a Windows 10 Client virtual machine connected through a private Internal Network named Lab_Network. The Windows Server acts as the future Domain Controller, DNS, and DHCP server, while the Windows Client serves as the domain workstation for testing communication and Active Directory services.

## To allow internet access while maintaining isolated communication between the virtual machines, a NAT connection is also included in the topology. This setup simulates a small real-world enterprise network environment commonly used in IT infrastructure and system administration labs.

## This topology will be used throughout the repository for:
### Active Directory Deployment

### DNS & DHCP Configuration

### Domain Joining

### Group Policy Management

### Shared Folder & Permissions

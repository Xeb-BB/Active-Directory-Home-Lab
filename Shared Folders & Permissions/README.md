# Lab Module: Shared Folders & Permissions
## Introduction
### Data security and organized accessibility are critical pillars of IT infrastructure. This lab module walks you through the implementation of a centralized network file share. You will learn how to protect corporate data by building a dual-layer security matrix—combining Share Permissions and NTFS (Security) permissions—to ensure users can only access the files necessary for their specific organizational roles.

## Tools & Technologies Used
### Windows Server 2022 File Systems (NTFS-formatted volumes)

### Advanced Sharing Wizard (Network visibility management)

### Windows Security Properties (Disabling inheritance and defining ACLs)

### Active Directory Security Principals (Domain Users/Groups)

### File Explorer Drive Mapping Utility (Network path mounting)

## What to Expect in This Section
### A guide to provisioning a network-accessible folder allocation on a secondary data partition.

### A deep dive into removing default access groups (like the local "Everyone" or "Users" rules) to secure the perimeter.

### Instructions on disabling inheritance to convert and tailor explicit permissions for specific domain accounts.

### Client-side mapping instructions to mount the network resource cleanly under a dedicated drive letter (ex. Z:).

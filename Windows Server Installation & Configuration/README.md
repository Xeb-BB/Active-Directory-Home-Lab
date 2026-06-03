# Lab Module: Windows Server Installation & Configuration Lab

##  Introduction
This repository serves as a comprehensive, hands-on documentation guide for deploying and configuring a core corporate network infrastructure from scratch. Building an enterprise environment requires a systematic approach to system hardening, identity management, and network resource allocation. 

The primary objective of this lab is to transform a vanilla Windows Server installation into a fully functional, centralized Domain Controller (DC) capable of managing network identities, automating dynamic IP address assignments, and routing internal DNS names. 

---

##  Tools & Technologies Used
* **Operating System:** Windows Server (Desktop Experience)
* **Hypervisor:** Oracle VirtualBox (Virtual Machine Environment)
* **Identity Services:** Active Directory Domain Services (AD DS)
* **Network Infrastructure Services:** * **DNS (Domain Name System):** For local name resolution mapping and active domain directory locating.
  * **DHCP (Dynamic Host Configuration Protocol):** For automated IP address leasing and management across the network subnet.
* **Remote Management:** Built-in Windows Remote Desktop (RDP) / AnyDesk

---

##  What to Expect in this Repository
This project provides a step-by-step, execution-ready framework for infrastructure deployment. By exploring this repository, you will find:

1. **A Visualized Implementation Roadmap:** A unified Mermaid workflow tracking the deployment sequentially from bare-metal setup to a live forest domain.
2. **Phase-by-Phase Checklists:** Actionable configuration baselines covering everything from server renames and strict loopback static IP configurations to final Active Directory role promotions.
3. **Enterprise Best Practices:** Infrastructure design workflows, including crucial DSRM recovery measures, Kerberos time-synchronization alignment, and administrative access rights overrides.

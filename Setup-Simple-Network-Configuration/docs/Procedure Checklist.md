### Procedure Checklist

## 1. Physical Layer Connectivity
Connect: Attach the client and server device to the router using a network cable (Ethernet).

Verify: Confirm that both the WAN and LAN indicators on the router are blinking, signaling active data transmission.

## 2. Accessing the Admin Interface
Identify Gateway: Open Command Prompt (CMD) on the host machine and run ipconfig.

Navigate: Open a web browser and enter the default router IP address: 192.168.1.1.

Verify: Confirm the router login prompt appears in your browser.

## 3. Basic Network Configuration
Update IP: Within the ISP configuration portal, change the router’s IP address to 192.168.1.5.

Refresh Connection: Toggle the network adapter (Disable/Enable) on the host machine and power cycle (restart) the router.

Configure DHCP: Set the local DHCP range to 192.168.1.1 – 192.168.1.254. Client must recieved IP automatically.

Reserve Address: Set a static reservation for the server's IP to prevent other device use it. 

Verify: Run ipconfig on the client and server to ensure it has received an IP address within the new configuration.

## 4. Security Hardening
Access Control: Change the default administrator password to a strong, unique credential.

Wireless Security: Enable WPA3 (or WPA2 if WPA3 is incompatible) encryption for the Wireless SSID.

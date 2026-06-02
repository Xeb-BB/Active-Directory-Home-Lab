# Common Troubleshooting
## 1. Complete Communication Failure (Ping Fails)
### Problem: The Windows Client cannot ping the Windows Server's IP address (192.168.5.5).

### Cause: By default, Windows Firewall blocks ping requests on new networks.

### Evidence: Running ping 192.168.5.5 in the command prompt gives you: Request timed out.

### Solution: On the Windows Server, open Windows Defender Firewall -> click Inbound Rules -> find File and Printer Sharing (Echo Request - ICMPv4-In) -> right-click it and choose Enable Rule.

### Lesson Learned: A failed ping doesn't always mean your network cables or settings are broken. Security features like firewalls are built to drop connection requests silently. Turning on ping responses (ICMP) is always your first step to confirm your machines can actually see each other.

## 2. Wrong IP Address on Client (APIPA Loop)
### Problem: The Windows Client gets a broken, useless IP address and can't connect to the server.

### Cause: Either the Server's DHCP service is turned off, or you made a typo in the VirtualBox network names (breaking the link between them).

### Evidence: Running ipconfig on the Client shows an IP address starting with 169.254.x.x.

### Solution: 1. Check your VirtualBox settings for both VMs and make sure the network name (Lab_Network) matches exactly.
### 2. If they match, go to the Server, open services.msc, find DHCP Server, and click Restart.
### Lesson Learned: Whenever you see an IP address starting with 169.254, it means the client is looking for a network but cannot find a DHCP server. It instantly tells you that your problem is either a disconnected cable (mismatched network names) or a stopped service on the server.

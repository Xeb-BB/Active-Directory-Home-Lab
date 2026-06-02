# Using VirtualBox's Internal Network mode isolates your lab from your physical home network (preventing your lab DHCP server from messing up your home internet) while allowing the VMs to talk to each other.

## Internal Network Setup For Communication
### To link your Windows Server and Windows Client together, both virtual network cards must point to the exact same internal network name.

## Step 1: Configure the Windows Server VM
### In VirtualBox, make sure the Server VM is powered off.

### Right-click the Server VM -> Select Settings.

### Navigate to the Network tab on the left.

### Under Adapter 1, ensure Enable Network Adapter is checked.

### Change Attached to: from NAT to Internal Network.

### In the Name: dropdown/field, type a unique name for your private lab network (ex. Lab_Network).

### Expand the Advanced section -> Ensure Promiscuous Mode is set to Allow All.

### Click OK.

## Step 2: Configure the Windows Client VM
### Make sure the Client VM is powered off.

### Right-click the Client VM -> Select Settings.

### Navigate to the Network tab on the left.

### Under Adapter 1, ensure Enable Network Adapter is checked.

### Change Attached to: to Internal Network.

### In the Name: field, type or select the exact same name used for the server: Lab_Network.

#### *Note: If the names match perfectly, VirtualBox acts as an invisible virtual switch connecting the two machines together.*

### Expand Advanced -> Change Promiscuous Mode to Allow All.

### Click OK.

## Part 3: Verification (What to Expect)
### Boot both virtual machines.

### Assign a static IP address to your Windows Server (ex. 192.168.5.5).

### Once your DHCP lab module is completed later, your Windows Client will automatically pull a 192.168.5.x IP address from the server through this internal network link.

# Setting up DNS (Domain Name System) on a Windows Server 2022 Desktop Experience (GUI) machine.

## Step 1: Install Roles
### Open Server Manager -> Manage -> Add Roles and Features.
### Click Next until you reach Server Roles.
### Check DNS Server (click Add Features on the popup).
### Click Next to the end, check Restart automatically if required, and click Install.

## Step 2: Create Reverse Lookup Zone
### Open Server Manager -> Tools -> DNS.
### Right-click Reverse Lookup Zones -> New Zone... -> Next.
### Select Primary Zone + Store in Active Directory -> Next.
### Leave replication scope default -> Next.
### Select IPv4 Reverse Lookup Zone -> Next.
### Enter your Network ID (e.g., 192.168.5) -> Next.
### Leave Allow only secure dynamic updates selected -> Next -> Finish.

## Step 3: Create Server Pointer (PTR) Record
### Expand Reverse Lookup Zones and select your newly created zone.
### Right-click an empty space on the right pane -> New Pointer (PTR).
### Complete the Host IP Address field with your server's full IP (192.168.5.5).
### Click Browse -> Double-click your Server Name -> Double-click Forward Lookup Zones.
### Select your domain name (css.com), scroll down, select your server's Host (A) record or Start of Authority (SOA) record, and click OK.

## Step 4: Verify DNS via Client Command Line
### Once your client is connected to the same network as your server, open Command Prompt or PowerShell on the client machine and run these two verification commands:
### Test Forward Lookup (Name to IP)
### This tests if your client can find the server using its domain name.

### Command: nslookup

### Expected Result: Default Server: css.com and the Address: 192.168.5.5

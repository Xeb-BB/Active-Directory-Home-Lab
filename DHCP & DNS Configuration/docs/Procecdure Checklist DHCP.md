### Step 1: Install DHCP Server Role

1. Open Server Manager -> Manage -> Add Roles and Features.
2. Click Next until you reach Server Roles.
3. Check DHCP Server -> Click Add Features on the pop-up -> Click Next to the end.
4. Check Restart automatically if required and click Install -> Close.
---
### Step 2: Authorize DHCP in Active Directory

1. In Server Manager, click the Notifications Flag (yellow triangle) at the top right.
2. Click Complete DHCP configuration.
3. Click Next -> verify Domain Admin credentials -> click Commit -> Close.
---
### Step 3: Create and Configure DHCP Scope
1. Open Server Manager -> Tools -> DHCP.
2. Expand your server name -> right-click IPv4 -> select New Scope... -> Next.
3. Name: Enter `Client_LAN` -> Next.
4. IP Range Setup:
* *Start IP Address:* `192.168.5.1`
* *End IP Address:* `192.168.5.254`
* *Length:* `24` *(Subnet Mask auto-populates to `255.255.255.0`)* -> Next.

  
5. Exclusions: 192.168.5.5 (Server's IP) -> Next.
6. Lease Duration: Leave default (8 days) -> Next.
7. Options: Select *“Yes, I want to configure these options now”* -> Next.

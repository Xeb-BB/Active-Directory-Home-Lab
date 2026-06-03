```mermaid
flowchart TD
    Start([Start]) --> Step1[Step 1: Install DHCP Server Role<br>Server Manager -> Manage -> Add Roles and Features]
    Step1 --> Step1a[Click Next to Server Roles<br>Check DHCP Server & click Add Features]
    Step1a --> Step1b[Click Next to End<br>Check 'Restart automatically' -> Install -> Close]
    
    Step1b --> Step2[Step 2: Authorize DHCP in Active Directory<br>Server Manager -> Click Notifications Flag yellow triangle]
    Step2 --> Step2a[Click Complete DHCP configuration]
    Step2a --> Step2b[Click Next -> Verify Domain Admin credentials -> Commit -> Close]
    
    Step2b --> Step3[Step 3: Create and Configure DHCP Scope<br>Server Manager -> Tools -> DHCP]
    Step3 --> Step3a[Expand server name -> Right-click IPv4 -> New Scope -> Next]
    Step3a --> Step3b[Name: Client_LAN -> Next]
    Step3b --> Step3c[IP Range Setup<br>Start: 192.168.5.1<br>End: 192.168.5.254<br>Length: 24 Subnet Mask: 255.255.255.0 -> Next]
    Step3c --> Step3d[Exclusions: Add 192.168.5.5 Server IP -> Next]
    Step3d --> Step3e[Lease Duration: Leave default 8 days -> Next]
    Step3e --> Step3f[Options: Select 'Yes, I want to configure these options now' -> Next]
    
    Step3f --> End([End])

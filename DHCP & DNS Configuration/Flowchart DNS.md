```mermaid 
flowchart TD
    Start([Start]) --> Step1[Step 1: Install Roles<br>Server Manager -> Manage -> Add Roles and Features]
    Step1 --> Step1a[Click Next to Server Roles<br>Check DNS Server]
    Step1a --> Step1b[Click Next to End<br>Check 'Restart automatically' -> Install]
    
    Step1b --> Step2[Step 2: Create Reverse Lookup Zone<br>Server Manager -> Tools -> DNS]
    Step2 --> Step2a[Right-click Reverse Lookup Zones -> New Zone -> Next]
    Step2a --> Step2b[Select Primary Zone + Store in Active Directory -> Next]
    Step2b --> Step2c[Leave Replication Scope Default -> Next]
    Step2c --> Step2d[Select IPv4 Reverse Lookup Zone -> Next]
    Step2d --> Step2e[Enter Network ID: 192.168.5 -> Next]
    Step2e --> Step2f[Leave 'Allow only secure dynamic updates' -> Next -> Finish]
    
    Step2f --> Step3[Step 3: Create Server Pointer PTR Record<br>Expand Reverse Lookup Zones & select new zone]
    Step3 --> Step3a[Right-click empty space on right pane -> New Pointer PTR]
    Step3a --> Step3b[Enter Host IP Address: 192.168.5.5]
    Step3b --> Step3c[Click Browse -> Record Type: All Server --> Double-click Server Name -> Forward Lookup Zones]
    Step3c --> Step3d[Select css.com -> Select Host A or SOA record -> Click OK]
    
    Step3d --> Step4[Step 4: Verify DNS via Client Command Line<br>Connect client to same network & open CMD/PowerShell]
    Step4 --> Step4a[Run Command: nslookup]
    Step4a --> Dec1{Does output match?<br>Default Server: css.com<br>Address: 192.168.5.5}
    
    Dec1 -- Yes --> End([End])
    Dec1 -- No --> Fail[Troubleshoot Client Network / IP Settings]
    Fail --> Step4

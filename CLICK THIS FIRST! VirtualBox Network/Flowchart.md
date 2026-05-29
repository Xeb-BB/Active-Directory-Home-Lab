```mermaid

flowchart TD
    Start([Start]) --> Step1[Configure Windows Server VM<br>Power off Server VM -> Right-click -> Settings]
    Step1 --> Step1a[Go to Network tab -> Enable Network Adapter]
    Step1a --> Step1b[Change Attached to: Internal Network]
    Step1b --> Step1c[Set Name to: Lab_Network]
    Step1c --> Step1d[Expand Advanced -> Set Promiscuous Mode: Allow All -> Click OK]
    
    Step1d --> Step2[Configure Windows Client VM<br>Power off Client VM -> Right-click -> Settings]
    Step2 --> Step2a[Go to Network tab -> Enable Network Adapter]
    Step2a --> Step2b[Change Attached to: Internal Network]
    Step2b --> Step2c[Set Name to exact match: Lab_Network]
    Step2c --> Step2d[Expand Advanced -> Set Promiscuous Mode: Allow All -> Click OK]
    
    Step2d --> Step3[Verification<br>Boot both Virtual Machines]
    Step3 --> Step3a[Assign static IP to Server 192.168.5.5]
    Step3a --> Step3b[Client automatically receives 192.168.5.x via DHCP later]
    
    Step3b --> End([End])

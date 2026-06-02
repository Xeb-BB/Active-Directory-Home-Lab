```mermaid 
flowchart TD
    %% --- PHASE 1: JOINING THE DOMAIN ---
    subgraph Phase1 [ Phase 1: Joining the Domain On the Client Machine]
        Start([Start Domain Join Process])
        
        Step1[Open System Settings<br>Press Win + R, type 'sysdm.cpl', hit Enter]
        Step2[Initiate Change<br>On Computer Name tab, click 'Change...']
        
        Data1[Data Input:<br>Select 'Domain' radio button<br>Type: css.com]
        Step3[Enter Target Domain<br>Input domain data and click OK]
        
        Data2[Data Input:<br>Username: Administrator<br>Password: Domain Admin Password]
        Step4[Authenticate Domain Credentials<br>Provide requested credentials]
        
        Dec1{Credential &<br>Network Valid?}
        
        Step5[Confirm Welcome Message<br>Verify dialog: 'Welcome to the css.com domain.'<br>Click OK]
        Step6[System Reboot<br>Click Close -> Click Restart Now]
    end

    %% --- PHASE 2: POST-JOIN VERIFICATION ---
    subgraph Phase2 [ Phase 2: Post-Join Verification]
        Step7[First Domain Login<br>At lock screen, click 'Other User']
        
        Data3[Data Input:<br>Username: jbenriquez<br>Password: User's Password]
        Step8[Sign In with Domain Account<br>Enter lab user credentials]
        
        Step9[Verify Object in AD<br>Log into DC -> Open Active Directory Users and Computers]
        Step10[Navigate to 'Computers' Container]
        
        Dec2{Is Client Hostname<br>Populated in Database?}
        
        Success[Domain Join Successfully Verified]
        Fail[Troubleshoot Network / DNS Settings]
        End([End Domain Join Process])
    end

    %% --- Flow Connections ---
    Start --> Step1
    Step1 --> Step2
    Step2 --> Data1
    Data1 --> Step3
    Step3 --> Data2
    Data2 --> Step4
    Step4 --> Dec1
    
    Dec1 -- Yes / Success --> Step5
    Dec1 -- No / Error --> Fail
    
    Step5 --> Step6
    Step6 --> Step7
    Step7 --> Data3
    Data3 --> Step8
    Step8 --> Step9
    Step9 --> Step10
    Step10 --> Dec2
    
    Dec2 -- Yes --> Success
    Dec2 -- No --> Fail
    Success --> End

    %% --- Assigning Classes to Nodes ---
    class Step1,Step2,Step3,Step4,Step5,Step6,Step7,Step8,Step9,Step10 process;
    class Data1,Data2,Data3 data;
    class Dec1,Dec2 decision;
    class Start,Success,Fail endpoint;


flowchart TD
    %% --- Style Definitions ---
    classDef process fill:#f9f9f9,stroke:#333,stroke-width:2px;
    classDef data fill:#fff3cd,stroke:#ffc107,stroke-width:2px;
    classDef decision fill:#e2f0d9,stroke:#385723,stroke-width:2px;
    classDef endpoint fill:#d9e1f2,stroke:#1f4e78,stroke-width:3px;

    %% --- PHASE 3: JOINING THE DOMAIN ---
    subgraph Phase3 [🖥️ Phase 3: Joining the Domain On the Client Machine]
        Start([Start Domain Join Process]) class Start endpoint;
        
        Step1[Open System Settings<br>Press Win + R, type 'sysdm.cpl', hit Enter] class Step1 process;
        Step2[Initiate Change<br>On Computer Name tab, click 'Change...'] class Step2 process;
        
        Data1[Data Input:<br>Select 'Domain' radio button<br>Type: css.com] class Data1 data;
        Step3[Enter Target Domain<br>Input domain data and click OK] class Step3 process;
        
        Data2[Data Input:<br>Username: Administrator<br>Password: Domain Admin Password] class Data2 data;
        Step4[Authenticate Domain Credentials<br>Provide requested credentials] class Step4 process;
        
        Dec1{Credential &<br>Network Valid?} class Dec1 decision;
        
        Step5[Confirm Welcome Message<br>Verify dialog: 'Welcome to the css.com domain.'<br>Click OK] class Step5 process;
        Step6[System Reboot<br>Click Close -> Click Restart Now] class Step6 process;
    end

    %% --- PHASE 4: POST-JOIN VERIFICATION ---
    subgraph Phase4 [🔑 Phase 4: Post-Join Verification]
        Step7[First Domain Login<br>At lock screen, click 'Other User'] class Step7 process;
        
        Data3[Data Input:<br>Username: jbenriquez<br>Password: User's Password] class Data3 data;
        Step8[Sign In with Domain Account<br>Enter lab user credentials] class Step8 process;
        
        Step9[Verify Object in AD<br>Log into DC -> Open Active Directory Users and Computers] class Step9 process;
        Step10[Navigate to 'Computers' Container] class Step10 process;
        
        Dec2{Is Client Hostname<br>Populated in Database?} class Dec2 decision;
        
        Success([Domain Join Successfully Verified]) class Success endpoint;
        Fail([Troubleshoot Network / DNS Settings]) class Fail endpoint;
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

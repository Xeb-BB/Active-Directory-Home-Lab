```mermaid
flowchart TD
    Start([Start]) --> Step1[Step 1: Create OU & Move Targets<br>ADUC -> Right-click css.com -> New Organizational Unit]
    Step1 --> Step1a[Name OU Lab_Users -> Drag & drop target user jbenriquez into it]
    
    Step1a --> Step2[Step 2: Create New GPO<br>Group Policy Management -> Right-click Group Policy Objects -> New]
    Step2 --> Step2a[Name policy Restrict_Control_Panel -> Click OK]
    
    Step2a --> Step3[Step 3: Configure GPO Settings<br>Right-click new GPO -> Edit]
    Step3 --> Step3a[Navigate to: User Configuration -> Policies -> Administrative Templates -> Control Panel]
    Step3a --> Step3b[Double-click 'Prohibit access...' -> Set to Enabled -> Click OK -> Close Editor]
    
    Step3b --> Step4[Step 4: Link GPO to OU<br>Right-click Lab_Users OU -> Link an Existing GPO]
    Step4 --> Step4a[Select Restrict_Control_Panel -> Click OK --> Open CMD/PowerShell Run Command: gpupdate /force]
    
    Step4a --> Step5[Step 5: Enforce and Verify on Client<br>Log into client as jbenriquez -> Open CMD/PowerShell]
    Step5 --> Step5a[Run Command: gpupdate /force]
    Step5a --> Step5b[Physically attempt to open Control Panel to verify block]
    
    Step5b --> End([End])

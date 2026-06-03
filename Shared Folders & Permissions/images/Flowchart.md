```mermaid
flowchart TD
    Start([Start]) --> Step1[Step 1: Create Folder & Configure Share Permissions<br>Open data drive D:\ -> Right-click -> New -> Folder]
    Step1 --> Step1a[Name folder: Company_Share -> Right-click -> Properties -> Sharing tab]
    Step1a --> Step1b[Click Advanced Sharing -> Check 'Share this folder' -> Click Permissions]
    Step1b --> Step1c[Select Everyone -> Click Remove]
    Step1c --> Step1d[Click Add -> Type jbenriquez -> Click Check Names -> Click OK]
    Step1d --> Step1e[Select Domain Users -> Check 'Full Control' under Allow -> Click OK out to main properties]
    
    Step1e --> Step2[Step 2: Map Network Drive on Client<br>Copy Network Path from Sharing tab e.g., \\server-name\Company_Share]
    Step2 --> Step2a[Log into client machine as domain user jbenriquez]
    Step2a --> Step2b[Open File Explorer -> Right-click This PC -> Select Map network drive...]
    Step2b --> Step2c[Choose drive letter Z: -> Paste copied network path into Folder field]
    Step2c --> Step2d[Check 'Reconnect at sign-in' -> Click Finish]
    
    Step2d --> End([End])

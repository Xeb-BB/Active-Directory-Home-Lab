# This procedure outlines how to configure and deploy Group Policy Objects (GPOs) within a Windows Server 2022 environment to manage user permissions, enforce security restrictions, and standardize system configurations across domain-joined client machines. 

## Step 1: Create an OU and Move Targets
### Open Server Manager -> Tools -> Active Directory Users and Computers.
### Right-click your domain (css.com) -> New -> Organizational Unit.

### Name it (e.g., Lab_Users) -> Click OK.

### Drag and drop your target user (e.g., jbenriquez) into this new OU.

---

## Step 2: Create a New GPO
### Open Server Manager -> Tools -> Group Policy Management.

### Expand Forest -> Domains -> css.com.

### Right-click Group Policy Objects -> New.

### Name your policy Restrict_Control_Panel -> Click OK.

---

## Step 3: Configure GPO Settings
### Right-click your new GPO -> Click Edit....

### Navigate to your restriction path:

### User Path: User Configuration -> Policies -> Administrative Templates -> Control Panel.

### Double-click Prohibit access to Control Panel and PC settings.

### Change it to Enabled -> Click OK -> Close the Editor window.

---

## Step 4: Link GPO to the OU
### In the Group Policy Management window, right-click your created OU (Lab_Users).

### Click Link an Existing GPO....

### Select your policy (Restrict_Control_Panel) -> Click OK.
### Open Command Prompt or PowerShell and force the update:
#### *gpupdate /force*

---

## Step 5: Enforce and Verify on Client
### Log into the client machine as the domain user (jbenriquez).

### Open Command Prompt or PowerShell and force the update:
#### *gpupdate /force*
### Physically try to open the Control Panel to verify that Windows blocks access.

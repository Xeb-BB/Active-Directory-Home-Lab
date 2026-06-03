# Introduction: While Share permissions open the network gateway, NTFS Security permissions enforce the actual file-level restrictions (Read, Write, Modify) for users and groups accessing the data locally or over the network.

## Step 1: Disable Inheritance and Remove Default Access
### Right-click your shared folder (Company_Share) -> Select Properties.

### Navigate to the Security tab -> Click Advanced near the bottom.

### Click the Disable inheritance button.

### Select "Convert inherited permissions into explicit permissions on this object" when prompted.

### Select the standard local Users group from the list -> Click Remove. (Keep Administrators, SYSTEM, and any intended domain groups).

## Step 2: Assign Explicit Security Permissions
### Inside the Advanced Security Settings window, click Add.

### Click Select a principal at the top.

### Type the target domain user (e.g., jbenriquez) or your target domain group -> Click Check Names -> Click OK.

### Set the precise permission level:

#### *For Read/Write (Modify) Access: Check the box for Modify (this automatically selects Read & execute, List folder contents, Read, and Write).*

#### *For Read-Only Access: Ensure Modify and Write are unchecked; leave only Read & execute, List folder contents, and Read active.*

### Click OK to close the Permission Entry window.

### Click Apply -> OK -> OK to close all properties windows.

## Step 3: Verify Security Restrictions on Client
### Log into the client machine as the restricted domain user (jbenriquez).

### Access the mapped network drive (Z:).

### Perform a physical verification test based on your assigned security rules:

### If Read-Only: Attempt to create a new text file or folder inside the share. Verify that Windows pops up an "Access is Denied" security error.

### If Modify: Create, edit, and delete a file to ensure changes save successfully without permission prompts.

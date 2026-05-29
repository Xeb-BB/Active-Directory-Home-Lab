
## Step 1: Create Folder & Configure 

### 1. On your server's data drive (e.g., `D:\`), right-click -> **New** -> **Folder**. Name it `Company_Share`.
### 2. Right-click the folder -> **Properties** -> **Sharing** tab -> Click **Advanced Sharing...**.
### 3. Check **Share this folder** -> Click **Permissions**.
### 4. Select **Everyone** -> Click **Remove**.
### 5. Click **Add...** -> Type `jbenriquez` -> Click **Check Names** -> Click **OK**.
### 6. Select **Domain Users**, check **Full Control** under *Allow*, and click **OK** out to the main properties window.

---

## Step 2: Map Network Drive on Client

### 1. Copy the **Network Path** from the folder's *Sharing* tab (e.g., `\\server-name\Company_Share`).
### 2. Log into the client machine as a domain user (e.g., `jbenriquez`).
### 3. Open **File Explorer** -> Right-click **This PC** -> Select **Map network drive...**.
### 4. Choose a drive letter (e.g., `Z:`).
### 5. Paste the copied network path into the **Folder:** field.
### 6. Check **Reconnect at sign-in** -> Click **Finish**.

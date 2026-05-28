
## ⚙️ Phase 1: Initial Server Configuration
*Complete these baseline steps before touching any server roles to avoid configuration conflicts.*

### 1. Rename the Server
-  Open **Server Manager** and click **Local Server** on the left menu.
-  Click on the computer name link (e.g., `WIN-A1B2C3D4`).
-  In the *System Properties* window, click the **Change...** button.
-  Type your planned hostname (our host is SERVER) into the **Computer name** field.
-  Leave the member status as **WORKGROUP** (do not change the domain yet).
-  Click **OK**, close the properties windows, and select **Restart Now** when prompted.

### 2. Configure Static IP Address
-  After the reboot, right-click the network icon in the taskbar and select **Open Network & Internet settings**.
-  Click **Change adapter options**.
-  Right-click your active network adapter "Ethernet" and select **Properties**.
-  Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
-  Select **Use the following IP address** and input your network scheme:
  - **IP Address:** `[Your SERVER IP]`
  - **Subnet Mask:** `[Your Subnet Mask]`
-  **Crucial for AD:** Set the **Preferred DNS server** to `127.0.0.1` (the loopback address, ensuring the server points to its own local DNS services).
-  Click **OK** on both windows to apply changes.

### 3. Adjust Time Zone & Enable Remote Management
-  Go back to **Server Manager** -> **Local Server**.
-  Click the **Time zone** link, select your local time zone, and verify the clock matches perfectly.
-  Click the **Remote Desktop** link (Disabled by default).
-  Change it to **Allow remote connections to this computer**, click **OK** through the warning, and hit **Apply**.

### 4. Run Windows Update
-  Type `Windows Update` into the Windows search bar.
-  Click **Check for updates** and let the server download all critical security patches.
-  Reboot the system if required.

---

## 🔑 Phase 2: Role Installation & Configuration (Active Directory)
*Now that your baseline settings are locked in, build out the domain infrastructure.*

### 1. Add the AD DS and DNS Roles
-  Open **Server Manager**, click **Manage** in the top-right corner, and select **Add Roles and Features**.
-  Click **Next** until you reach *Installation Type*. Ensure **Role-based or feature-based installation** is selected.
-  Click **Next** to confirm your server is highlighted in the server pool selection.
-  On the *Server Roles* list, check the box for **Active Directory Domain Services (AD DS)**.
-  On the popup prompt, click **Add Features**.
-  On the same list, check the box for **DNS Server**,**DHCP Server**. Click **Continue** on the prompt.
-  Click **Next** through *Features*, *AD DS*, *DNS Server* and **DHCP Server** screens without altering any defaults.
-  On the final confirmation screen, click **Install**. Wait for the progress bar to complete.

### 2. Promote Server to a Domain Controller
-  Click the yellow **Notification Flag** at the top of Server Manager.
-  Click **Promote this server to a domain controller**.
-  In the *Deployment Configuration* wizard, select the **Add a new forest** radio button.
-  In the **Root domain name** field, type your target domain (our ex. is `css.com`). Click **Next**.
-  Input a strong password into the **Directory Services Restore Mode (DSRM)** fields. Click **Next**.
-  Proceed through the *DNS Options* and *Additional Options* (where your NetBIOS name like `CSS` will auto-populate).
-  Click **Next** through the *Paths* and *Review Options* screens.
-  The wizard will run a **Prerequisites Check**. Once the green checkmark confirms all prerequisite checks passed successfully, click **Install**.

> **Note:** The server will automatically configure itself, sign you out, and reboot. Upon loading, authenticate using your new Domain Administrator credentials ("CSS\Administrator").

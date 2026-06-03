### 1. Build the Organizational Unit (OU) Hierarchy
-  Open **Server Manager** -> **Tools** (top right) -> **Active Directory Users and Computers**.
-  Right-click your root domain (e.g., "css.com") -> **New** -> **Organizational Unit**.
-  Create a top-level OU named "Corporate" (or your preferred company name).
  - *Tip: Keep "Protect container from accidental deletion" checked.*
-  Inside your top-level OU, create the following sub-OUs to segregate resources cleanly:
  -  "Departments" (For standard business units)
  -  "Groups" (For security and distribution groups)
  -  "Users" (For standard employee user accounts)
  -  "Computers" (For workstation objects)

### 2. User Onboarding & Principle of Least Privilege
-  Right-click your "Users" OU -> **New** -> **User**.
-  Input user details (e.g., User logon name: "jbenriquez" and "jcenriquez").
-  Assign a temporary complex password and ensure **"User must change password at next logon"** is checked.

### 3. Validate Account Control Security Policy
-  Log in to a domain-joined client machine or a secondary session using one of the newly created standard user accounts.
-  Verify the user can successfully authenticate against the "css.com" domain.

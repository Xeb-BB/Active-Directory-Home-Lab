# Troubleshooting: Joining the Domain
## 1. Domain Controller Not Found
### Problem: The client machine cannot find the css.com domain.

### Cause: The client is using a public internet router for DNS instead of your Windows Server.

### Evidence: An error message says: "The network path was not found."

### Solution: On the Windows Client, open your IPv4 settings and manually change the Preferred DNS Server to match your Windows Server's static IP (192.168.5.5).

### Lesson Learned: DNS is everything in Active Directory. Computers find the domain controller by asking DNS where it is. If your DNS points to the internet, the client gets lost and cannot see your lab server.

## 2. Wrong Login Credentials
### Problem: Windows rejects your login attempt when trying to join the domain.

### Cause: A simple typo, or you are using the client's local account instead of the server's administrator account.

### Evidence: A pop-up tells you: "The username or password is incorrect."

### Solution: Make sure you are typing the Server's admin password. Use the format css\Administrator to force it to check the domain.

### Lesson Learned: Context matters. Joining a network domain requires domain-level permissions, so a local computer account will always fail.

## 3. Name Already Taken
### Problem: The client machine refuses to join the domain.

### Cause: A computer with the exact same name already exists in the Active Directory database from an old lab run.

### Evidence: An error says: "A computer account with this name already exists."

### Solution: On the Windows Server, open Active Directory Users and Computers, go to the Computers folder, right-click the old machine name, and click Delete.

### Lesson Learned: Active Directory requires every computer name to be completely unique. Always clean up old records before trying to join a new machine with the same name.

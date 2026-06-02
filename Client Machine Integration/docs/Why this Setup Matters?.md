# Why These Configurations Matter
## 1. Changing DNS to the Server's IP
### - Your home internet doesn't know your private domain css.com exists.
### - Active Directory relies completely on DNS to find things. When you type css.com, the client machine asks its DNS server: "Where is the Domain Controller?" If it asks the internet, it gets lost. Pointing the client's DNS to your server ensures it finds the right machine.

## 2. Using Domain Admin Credentials to Join
### - You cannot add a computer to a secure network database without explicit permission from the gatekeeper.

### - Joining a domain creates a highly secure, trusted bond between the client and the server. If any standard user could add computers to the network, anyone could plug a rogue device into the company environment. Requiring an Admin account keeps the database secure.

## 3. Rebooting Post-Join
### - Windows cannot switch its entire identity from a standalone computer to a domain member while it is running.

### - A reboot completely changes how the computer boots up. Instead of checking its own local database for users, it loads security protocols (like Kerberos) and reaches out over the network to let the Windows Server handle logins and push company policies.

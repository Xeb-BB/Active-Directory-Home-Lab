# In an enterprise IT environment, Active Directory (AD) accounts for a massive percentage of daily helpdesk tickets. The most common AD tickets generally fall into a few predictable categories, ranging from quick identity fixes to access provisioning.

# Identity & Credentials (The High-Volume Tickets)
### These tickets make up the vast majority of daily helpdesk queues and are usually the quickest to resolve.
### Password Resets: Users forgetting their passwords, entering expired credentials, or getting locked out of their accounts after returning from a vacation.
### Account Lockouts: Users entering an old password on a mobile device or a secondary workstation, causing background synchronization attempts to repeatedly trigger an account lockout policy.
### Expired Accounts: Temporary workers, contractors, or employees returning from an extended leave whose accounts hit a pre-configured expiration date.

# Access Control & Provisioning
### These tickets are slightly more complex, as they often require administrative approval workflows before IT can take action.
### Security Group Modifications: Users requesting access to a specific network resource, software license, or email distribution list that relies on AD security group membership for access.
### New User Onboarding: HR submitting a ticket to provision a new employee. This requires creating a new AD account, putting them in the correct Organizational Unit (OU), applying baseline security templates, and setting up an initial temporary password.
### Offboarding / Deprovisioning: Terminating access for an employee who is leaving the company. This usually involves disabling the account, moving it to an "Inactive" OU, stripping group memberships, and resetting the password.

## File Shares & Resources
### When users cannot access the data they need to do their jobs, these tickets quickly escalate in priority.
### Broken Network Drive Mapping: A user logs in and notices their shared drive (e.g., Z: drive) is missing or showing a red "X." This is usually fixed by checking Group Policy updates or mapping the folder manually.
### "Access Denied" on Shared Folders: Users attempting to access a folder on the network file server but failing because their account lacks the proper NTFS or Share permissions, requiring an admin to adjust the folder's Access Control List (ACL).

## Network & Client Sync Infrastructure
### These tickets typically impact multiple users at once or occur right after a machine is reassigned.
### Trust Relationship Failures: A user sees the dreaded message: "The trust relationship between this workstation and the primary domain failed." This happens when a client computer's machine account password falls out of sync with Active Directory, requiring the admin to unjoin and rejoin the workstation to the domain.
### Group Policy Not Applying: A machine isn't receiving a new software deployment, wallpaper, or security restriction. Admins usually resolve this by running troubleshooting commands like gpupdate /force or checking for local network/DNS issues.


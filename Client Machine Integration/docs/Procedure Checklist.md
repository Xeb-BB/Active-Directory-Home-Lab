# Joining the Domain (On the Client Machine)
### Now that the client can talk to the server, it’s time to perform the domain join.
--- 
## Open System Settings

### Press Win + R, type sysdm.cpl, and hit Enter to open the classic System Properties utility.

## Initiate Change

### On the Computer Name tab, click the Change... button near the bottom.

## Enter Target Domain

### Under the Member of section, select the Domain radio button.

### Type your full Active Directory domain name (css.com) and click OK.

## Authenticate Domain Credentials

### When the Windows Security prompt appears, provide credentials for an account authorized to join machines to the domain:

### *Username: Administrator*

### *Password: [Domain Admin Password]* 

## Confirm Welcome Message

### Wait for the dialogue box reading: "Welcome to the [css.com] domain." Click OK. (From our previous lab)

## System Reboot

### Click Close on the remaining system properties windows and click Restart Now to apply the configuration changes.

# Post-Join Verification
## First Domain Login

### At the client Windows lock screen, click Other User in the bottom-left corner.

## Sign In with Domain Account

### Authenticate using a valid domain user account environment:

### Format: USername: jbenriquez Password: (user's password) (From our previous lab)

## Verify Object in Active Directory (On the Server)

### Log into your Domain Controller.

### Open Active Directory Users and Computers.

### Navigate to the Computers container and verify that the client machine's hostname is populated in the database.

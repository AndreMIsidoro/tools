# PowerView

## Overview

PowerView is series of functions that performs network and Windows domain enumeration and exploitation.

## Functions

### Get-Domain

```
#Retrieves information about the current Active Directory domain
Get-Domain

#Enumerate Other Domains
Get-Domain -Domain <domain_name>

```
### Get-DomainGroupMember

Retrieves domain group specific information

    Get-DomainGroupMember -Identity "Domain Admins" -Recurse

### Get-DomainPolicy

Retrieves Group Policy settings related to the domain, specifically the Default Domain Policy and Default Domain Controllers Policy

```
Get-DomainPolicy

#Will show us the policy configurations of the Domain about system access or kerberos
Get-DomainPolicy | Select-Object -ExpandProperty SystemAccess
Get-DomainPolicy | Select-Object -ExpandProperty KerberosPolicy
```

### Get-DomainUser

Retrieves information about a domain user.

We can find users with SPN set:

    Get-DomainUser -SPN -Properties samaccountname,ServicePrincipalName

### Get-DomainTrustMapping

Enumerates the domain trust mappings

    Get-DomainTrustMapping

### Set-DomainUserPassword

The Set-DomainUserPassword cmdlet is used in PowerShell to change or set the password for a user account in an Active Directory domain.
We can specify as which user we want to run the cmdlet as, but if we want to do it as the user we are logged in as, we only need to specify the target user:

    $SecPassword = ConvertTo-SecureString '<new_password>' -AsPlainText -Force
    Set-DomainUserPassword -Identity <User_which_password_is_gonna_change> -AccountPassword $SecPassword

For example:

    $SecPassword = ConvertTo-SecureString 'Password123!' -AsPlainText -Force
    Set-DomainUserPassword -Identity Jacob.Surname -AccountPassword $SecPassword

### Test-AdminAccess

Test for local admin access on either the current machine or a remote one:

    Test-AdminAccess -ComputerName <hostname>

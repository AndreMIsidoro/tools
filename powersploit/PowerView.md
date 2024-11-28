# PowerView

## Overview

PowerView is series of functions that performs network and Windows domain enumeration and exploitation.

## Functions

### Set-DomainUserPassword

The Set-DomainUserPassword cmdlet is used in PowerShell to change or set the password for a user account in an Active Directory domain.
We can specify as which user we want to run the cmdlet as, but if we want to do it as the user we are logged in as, we only need to specify the target user:

    $SecPassword = ConvertTo-SecureString '<new_password>' - AsPlainText - Force
    Set-DomainUserPassword -Identity <User_which_password_is_gonna_change> -AccountPassword $SecPassword

For example:

    $SecPassword = ConvertTo-SecureString 'Password123!' - AsPlainText - Force
    Set-DomainUserPassword -Identity Jacob.Surname -AccountPassword $SecPassword

---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/set-csgrouppickupuserorbit
schema: 2.0.0
title: Set-CsGroupPickupUserOrbit
---

# Set-CsGroupPickupUserOrbit

## SYNOPSIS
Use the `Set-CsGroupPickupUserOrbit` cmdlet to modify an Enterprise Voice user's group pickup orbit number.

## SYNTAX

```
Set-CsGroupPickupUserOrbit [-User] <String> -Orbit <String> [-Confirm] [-Force] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
The same orbit can be assigned to multiple users.
This cmdlet will throw an exception if the user is not assigned a group pickup orbit number, or if the specified orbit does not exist or is of the wrong type.

## EXAMPLES

### Example 1
```
Set-CsGroupPickupUserOrbit "Ken Myer" -Orbit "*101"
```

This example replaces the user's current group pickup orbit number with orbit *101.
User is a positional parameter.
The first parameter after the cmdlet is assumed to be the User parameter value.
In this case, the display name "Ken Myer".


## PARAMETERS

### -Force

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Suppresses the display of any non-fatal error messages and completes the cmdlet operation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Orbit

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Specifies the new group pickup orbit number to be assigned to the user.
The number must be within an orbit pickup range that was created with a type of GroupPickup.
For more information on creating call park orbits, see [New-CsCallParkOrbit](https://learn.microsoft.com/powershell/module/skype/New-CsCallParkOrbit).

Values for the Orbit parameter must match the regular expression (\[\*|#\]?\[1-9\]\d{0,7})|(\[1-9\]\d{0,8}).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Specifies the user whose group pickup orbit number will be modified.
Because User is a positional parameter, the -User syntax is not required.
The first parameter after the cmdlet is assumed to be the User parameter value.

Users can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer) and 4) the user's Active Directory display name (for example, Ken Myer).
You can also reference a user account by using the user's Active Directory distinguished name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DisplayName, SipAddress, Identity

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Confirm

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
This cmdlet supports pipelined input from the `Get-CsUser` cmdlet.

## OUTPUTS

### Microsoft.Rtc.Management.Voice.Helpers.GroupPickup.DisplayGroupPickupUserOrbit
This cmdlet returns an instance of the Microsoft.Rtc.Management.Voice.Helpers.GroupPickup.DisplayGroupPickupUserOrbit object.

## NOTES

## RELATED LINKS

---
applicable: Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/grant-cscallviaworkpolicy
schema: 2.0.0
title: Grant-CsCallViaWorkPolicy
---

# Grant-CsCallViaWorkPolicy

## SYNOPSIS
Use the Grant-CsCallViaWorkPolicy cmdlet to assign call via work policies to a user or group of users.
Call via work policies enable and manage the characteristics of outbound calls placed through the Skype for Business client.

## SYNTAX

```
Grant-CsCallViaWorkPolicy [-Identity] <UserIdParameter> [-PolicyName] <String> [-Confirm]
 [-DomainController <Fqdn>] [-PassThru] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet assigns an existing per-user call via work policy to a user. Call via work policies are used to control access to the feature and manage the characteristics of outbound calls placed through the Skype for Business client.


## EXAMPLES

### Example 1 (Skype for Business Server 2015)
```

Grant-CsCallViaWorkPolicy -Identity "Ken Myer" -PolicyName StandardUserCvW
```

This example assigns the policy named "StandardUserCvW" to "Ken Myer".


## PARAMETERS

### -DomainController

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables you to specify the fully qualified domain name (FQDN) of a domain controller to be contacted when assigning the new policy.
If this parameter is not specified, then the Grant-CsCallViaWorkPolicy cmdlet will contact the first available domain controller.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Specifies a unique identifier of the user account the policy should be assigned to.
User identities can be specified by using one of four formats.

SIP address

User Principal Name (UPN)

Domain name and logon name, in the form domain\logon

Active Directory display name (Ken Myer), or distinguished name

In addition, you can use the asterisk (\*) wildcard character when using the display name as the user Identity.
For example, the Identity "\* Smith" grants the policy all users who have a display name that ends in the string value " Smith".

```yaml
Type: UserIdParameter
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables you to pass a user object through the pipeline that represents the user being assigned the policy.
By default, the Grant-CsCallViaWorkPolicy cmdlet does not pass objects through the pipeline.

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

### -PolicyName

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Specifies the name of the policy to be assigned.
The PolicyName is the policy identity minus the policy scope ("tag:").
A policy that has an identity of "Tag:Redmond" has a PolicyName of "Redmond".
A policy with the identity "Tag:RedmondCalloutPolicy" has a PolicyName of "RedmondCalloutPolicy".
If you set PolicyName to a null value, then the command will unassign any individual policy assigned to the user.
For example: `Grant-CsCallViaWorkPolicy -Identity "Ken Myer" -PolicyName $Null`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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

The WhatIf switch causes the command to simulate its results. By using this switch, you can view what changes would occur without having to commit those changes.

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
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Remove-CsCallViaWorkPolicy](Remove-CsCallViaWorkPolicy.md)

[Set-CsCallViaWorkPolicy](Set-CsCallViaWorkPolicy.md)

[New-CsCallViaWorkPolicy](New-CsCallViaWorkPolicy.md)

[Get-CsCallViaWorkPolicy](Get-CsCallViaWorkPolicy.md)

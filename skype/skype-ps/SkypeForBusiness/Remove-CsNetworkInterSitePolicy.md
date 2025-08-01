---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy
schema: 2.0.0
title: Remove-CsNetworkInterSitePolicy
---

# Remove-CsNetworkInterSitePolicy

## SYNOPSIS
Removes a network inter-site policy that defines bandwidth limitations between sites that are directly linked within a call admission control (CAC) configuration.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Remove-CsNetworkInterSitePolicy [-Identity] <XdsGlobalRelativeIdentity> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.
This cmdlet removes a network site policy that associates a bandwidth limitation policy with two directly connected sites.


## EXAMPLES

### Example 1
```
Remove-CsNetworkInterSitePolicy -Identity Reno_Portland
```

This example removes the network site policy with the Identity Reno_Portland.


### Example 2
```
Get-CsNetworkInterSitePolicy | Remove-CsNetworkInterSitePolicy
```

In Example 2, we remove all network site policies defined within the CAC configuration.
We begin by calling the `Get-CsNetworkInterSitePolicy` cmdlet to retrieve a collection of all network site policies.
That collection is then piped to the `Remove-CsNetworkInterSitePolicy` cmdlet, which removes each item in the collection.


## PARAMETERS

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Suppresses any confirmation prompts that would otherwise be displayed before making changes.

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

### -Identity

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The unique identifier of the network site policy you want to remove.
Network site policies are created only at the global scope, so this identifier does not need to specify a scope.
Instead, it contains a string that is a unique name that identifies that site policy.

```yaml
Type: XdsGlobalRelativeIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

### Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType

Accepts pipelined input of network inter-site policy objects.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType
This cmdlet does not return a value.
It removes an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkSitePolicyType.

## NOTES

## RELATED LINKS

[New-CsNetworkInterSitePolicy](New-CsNetworkInterSitePolicy.md)

[Set-CsNetworkInterSitePolicy](Set-CsNetworkInterSitePolicy.md)

[Get-CsNetworkInterSitePolicy](Get-CsNetworkInterSitePolicy.md)

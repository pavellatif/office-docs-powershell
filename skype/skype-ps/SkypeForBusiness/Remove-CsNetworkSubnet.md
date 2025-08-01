---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/remove-csnetworksubnet
schema: 2.0.0
title: Remove-CsNetworkSubnet
---

# Remove-CsNetworkSubnet

## SYNOPSIS
Removes an existing network subnet.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Remove-CsNetworkSubnet [-Identity] <XdsGlobalRelativeIdentity> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Each subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.
Use this cmdlet to remove a network subnet.


## EXAMPLES

### Example 1
```
Remove-CsNetworkSubnet -Identity 172.11.15.0
```

This example removes the subnet with the Identity (the Subnet ID) 172.11.15.0.


### Example 2
```
Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"} | Remove-CsNetworkSubnet
```

Example 2 removes all subnets associated with the Vancouver site.
To do this, we begin by calling the `Get-CsNetworkSubnet` cmdlet.
This will retrieve a collection of all subnets defined within the Skype for Business Server deployment.
This collection of subnets is then piped to the `Where-Object` cmdlet.
The `Where-Object` cmdlet takes that collection and narrows it down to only those subnets with a NetworkSiteID equal to (-eq) Vancouver.
Now that the collection consists only of subnets associated with the Vancouver site, we pipe the collection to the `Remove-CsNetworkSubnet` cmdlet, which removes every item in the collection.


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

The unique subnet ID of the subnet you want to remove.
This value will be an IP address (such as 174.11.12.0).

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

### Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType

Accepts pipelined input of network subnet objects.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType
This cmdlet does not return a value.
It removes an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType.

## NOTES

## RELATED LINKS

[New-CsNetworkSubnet](New-CsNetworkSubnet.md)

[Set-CsNetworkSubnet](Set-CsNetworkSubnet.md)

[Get-CsNetworkSubnet](Get-CsNetworkSubnet.md)

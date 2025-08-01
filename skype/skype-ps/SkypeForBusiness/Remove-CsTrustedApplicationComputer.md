---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/remove-cstrustedapplicationcomputer
schema: 2.0.0
title: Remove-CsTrustedApplicationComputer
---

# Remove-CsTrustedApplicationComputer

## SYNOPSIS
Removes a trusted application computer.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Remove-CsTrustedApplicationComputer [-Identity] <XdsGlobalRelativeIdentity> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
It is recommended that the computers that are running trusted applications within a Skype for Business Server deployment be added to a separate pool that is only for trusted applications.
However, you can add trusted application computers to an existing pool that is also used for other purposes.
Use this cmdlet to remove a trusted application computer.

When you use this cmdlet to remove a trusted application computer, it will be removed not only from the list of trusted application computers but from the list of computers available on Skype for Business Server.
In other words, if you call the `Get-CsTrustedApplicationComputer` cmdlet or the `Get-CsComputer` cmdlet the computer will no longer be listed.
You cannot remove a trusted application computer if it's the only computer on the pool.
If you want to remove the only computer on a pool you must remove the entire pool (which can be done by calling the `Remove-CsTrustedApplicationPool` cmdlet).


## EXAMPLES

### Example 1
```
Remove-CsTrustedApplicationComputer -Identity Trust1.litwareinc.com
```

This example removes the computer with the FQDN Trust1.litwareinc.com.


### Example 2
```
Get-CsTrustedApplicationComputer -Filter Trust* | Remove-CsTrustedApplicationComputer
```

This example removes all trusted computers that have FQDNs beginning with the string Trust.
The example begins by calling the `Get-CsTrustedApplicationComputer` cmdlet, passing the Filter parameter the value Trust*.
This will retrieve all trusted application computers with an FQDN beginning with Trust and ending with any set of characters.
That collection of computers is then piped to the `Remove-CsTrustedApplicationComputer` cmdlet, which removes each item (each computer) in the collection.
Keep in mind that this won't remove the computers from a pool if removing those computers would result in an empty pool.


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

The fully qualified domain name (FQDN) of the computer to remove.

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

### Microsoft.Rtc.Management.Xds.DisplayComputer

Accepts pipelined input of trusted application computer objects.

## OUTPUTS

### None
This cmdlet does not return a value.
It removes an object of type Microsoft.Rtc.Management.Xds.DisplayComputer.

## NOTES

## RELATED LINKS

[New-CsTrustedApplicationComputer](New-CsTrustedApplicationComputer.md)

[Get-CsTrustedApplicationComputer](Get-CsTrustedApplicationComputer.md)

[Remove-CsTrustedApplicationPool](Remove-CsTrustedApplicationPool.md)

[Get-CsTrustedApplicationPool](Get-CsTrustedApplicationPool.md)

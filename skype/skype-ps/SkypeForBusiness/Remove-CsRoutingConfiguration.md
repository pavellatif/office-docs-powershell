---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/remove-csroutingconfiguration
schema: 2.0.0
title: Remove-CsRoutingConfiguration
---

# Remove-CsRoutingConfiguration

## SYNOPSIS
Resets the routing configuration to its default settings.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Remove-CsRoutingConfiguration [-Identity] <XdsIdentity> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Voice routes contain instructions that tell Skype for Business Server how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).
This cmdlet removes the global (and only) routing configuration, which is a container for all voice routes defined for a Skype for Business Server deployment.
"Removing" the routing configuration doesn't actually remove it; the Global (and only) instance is still there.
However, it does set the list of voice routes to the default settings.

WARNING: Removing the routing configuration (in other words, setting the list of voice routes to the default) deletes all defined voice routes for a Skype for Business Server deployment and replaces them with a single route with default settings.


## EXAMPLES

### Example 1
```
Remove-CsRoutingConfiguration -Identity Global -Confirm
```

This example resets the Global (and only) routing configuration to the default settings.
This action deletes all defined voice routes, so we added the Confirm parameter in order to receive a prompt asking whether we really want to perform this action before the removal takes place.


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

The scope of the routing configuration to remove.
This value must be Global.

```yaml
Type: XdsIdentity
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

### Microsoft.Rtc.Management.Policy.Voice.PSTNRoutingSettings

Accepts pipelined input of a routing configuration object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-CsRoutingConfiguration](New-CsRoutingConfiguration.md)

[Set-CsRoutingConfiguration](Set-CsRoutingConfiguration.md)

[Get-CsRoutingConfiguration](Get-CsRoutingConfiguration.md)

[Remove-CsVoiceRoute](Remove-CsVoiceRoute.md)

[Get-CsVoiceRoute](Get-CsVoiceRoute.md)

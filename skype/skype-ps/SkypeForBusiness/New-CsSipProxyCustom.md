---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/new-cssipproxycustom
schema: 2.0.0
title: New-CsSipProxyCustom
---

# New-CsSipProxyCustom

## SYNOPSIS

Used to assign a custom realm (SIP Communications Service) to a collection of proxy configuration settings.
Realms (also known as protection domains) are used to authenticate user credentials during logon.
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

```
New-CsSipProxyCustom -CustomValue <String> [<CommonParameters>]
```

## DESCRIPTION

Each proxy server must be associated with a realm; realms (also known as protection domains) indicate where a user's logon credentials should be processed.
By default, Skype for Business Server uses SIP Communications Service as its default realm; however, it is possible to change the realm used by a proxy server.
This is done by creating a SipProxy.Custom object and then assigning that object to the Realm property of the appropriate proxy server (or servers).
You can create a custom realm by using the New-CsSipProxyCustom cmdlet.



## EXAMPLES

### EXAMPLE 1
```

$x = New-CsSipProxyCustom -CustomValue "Litwareinc Communications Service"
```

The command shown in Example 1 assigns a custom realm (Litwareinc Communications Service) to a variable named $x.


## PARAMETERS

### -CustomValue

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Name of the realm to be used for authentication purposes.

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

### CommonParameters
This cmdlet supports the common parameters: `-Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).`

## INPUTS

### None
The New-CsSipProxyCustom cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.Custom
The New-CsSipProxyCustom cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.Custom object.

## NOTES

## RELATED LINKS

[New-CsSipProxyRealm](New-CsSipProxyRealm.md)

[New-CsSipProxyUseDefault](New-CsSipProxyUseDefault.md)

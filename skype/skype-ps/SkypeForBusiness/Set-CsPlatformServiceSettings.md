---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/set-csplatformservicesettings
schema: 2.0.0
title: Set-CsPlatformServiceSettings
---

# Set-CsPlatformServiceSettings

## SYNOPSIS
Modifies the Skype for Business on Mac capabilities in your organization. This cmdlet was introduced in Skype for Business Server 2015 Cumulative Update 6 (December 2017).

## SYNTAX

### Identity (Default)
```
Set-CsPlatformServiceSettings [-EnableDelegateManagement <Boolean>] [-EnableExternalAccessCheck <Boolean>]
 [-EnablePushNotifications <Boolean>] [-UseLegacyPushNotifications <Boolean>] [-EnableE911 <Boolean>]
 [-EnableFileTransfer <Boolean>] [-EnableCORS <Boolean>] [-EnableUcwaScopeCheck <Boolean>]
 [-MaxRegistrationsPerPublicApplication <Int32>] [[-Identity] <XdsIdentity>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Instance
```
Set-CsPlatformServiceSettings [-EnableDelegateManagement <Boolean>] [-EnableExternalAccessCheck <Boolean>]
 [-EnablePushNotifications <Boolean>] [-UseLegacyPushNotifications <Boolean>] [-EnableE911 <Boolean>]
 [-EnableFileTransfer <Boolean>] [-EnableCORS <Boolean>] [-EnableUcwaScopeCheck <Boolean>]
 [-MaxRegistrationsPerPublicApplication <Int32>] [-Instance <PSObject>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Skype for Business Server 2015 Cumulative Update 6 introduces new features for Skype for Business on Mac users like support for E-911 calls, send files in peer-to-peer chats, block external access by policy and more.

The `Set-CsPlatformServiceSettings` cmdlet gives you control to enable or disable these features.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Set-CsPlatformServiceSettings -EnableDelegateManagement $False -EnableExternalAccessCheck $True -EnableE911 $False -EnableFil
eTransfer $True
```

This example modifies some parameters for global platform service settings.

## PARAMETERS

### -EnableCORS

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is reserved for Microsoft internal use only.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDelegateManagement

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables the ability to manage delegates from the Skype for Business on Mac client.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableE911

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Allows Skype for Business on Mac users to call 911.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableExternalAccessCheck

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables administrators to use external access policies to block external access to Skype for Business on Mac users.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableFileTransfer

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables Skype for Business on Mac users send files in peer-to-peer chats.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnablePushNotifications

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Enables Skype for Business on Mac clients to use push notifications.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableUcwaScopeCheck

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is reserved for Microsoft internal use only.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Suppresses any confirmation prompts that would otherwise be displayed before testing.

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

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Indicates the Identity of the Platform Service Settings to be modified.

```yaml
Type: XdsIdentity
Parameter Sets: Identity
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values. You can retrieve this object reference by calling the Get-CsPlatformServiceSettings cmdlet.

```yaml
Type: PSObject
Parameter Sets: Instance
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxRegistrationsPerPublicApplication

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is reserved for Microsoft internal use only.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLegacyPushNotifications

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is reserved for Microsoft internal use only.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Prompts you for confirmation before running the cmdlet.

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

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.PSObject


## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS
[New-CsPlatformServiceSettings](https://learn.microsoft.com/powershell/module/skype/new-csplatformservicesettings?view=skype-ps)

[Get-CsPlatformServiceSettings](https://learn.microsoft.com/powershell/module/skype/get-csplatformservicesettings?view=skype-ps)

[Remove-CsPlatformServiceSettings](https://learn.microsoft.com/powershell/module/skype/remove-csplatformservicesettings?view=skype-ps)

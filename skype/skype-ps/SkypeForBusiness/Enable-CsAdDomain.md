---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/enable-csaddomain
schema: 2.0.0
title: Enable-CsAdDomain
---

# Enable-CsAdDomain

## SYNOPSIS
Modifies the security settings on the universal groups created during forest preparation.
These modifications provide the permissions needed to host and manage users enabled for Skype for Business Server within the domain.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

```
Enable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-SkipPrepareCheck <Boolean>] [-CrossForest]
 [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] [-Force] [-Report <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Before you can install Skype for Business Server in a domain, that domain must be correctly prepared, a process that includes extending the Active Directory schema to allow for the addition of attributes specific to Skype for Business Server as well as assigning the required Access Control Entries to the universal groups needed for managing and operating Skype for Business Server.
Domain preparation is typically carried out through the Skype for Business Server Setup Wizard.
However, administrators can also perform domain preparation by running the Enable-CsAdDomain cmdlet.

After the Enable-CsAdDomain cmdlet finishes running, you can use the Get-CsAdDomain cmdlet to verify that the domain is ready for the next step in the installation process.

If you receive the following error, "Cannot find the object 'CrossRef' in Active Directory" while running tasks to prepare a child domain of a single-forest environment with multiple domains, you may have to manually add the RTCComponentUniversalServices group from the parent domain to the Windows Authorization Access group in the child domain.

Historical Note: This cmdlet carries out tasks similar to those carried out by the following Microsoft Office Communications Server 2007 R2 command:

`Lcscmd.exe /domain /action:DomainPrep`


## EXAMPLES

### Example 1
```
Enable-CsAdDomain
```

The command shown in Example 1 prepares the local domain for the installation of Skype for Business Server.

### Example 2
```
Enable-CsAdDomain -Domain asia.litwareinc.com
```

Example 2 prepares the domain asia.litwareinc.com for the installation of Skype for Business Server.


## PARAMETERS

### -CrossForest

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

If present, indicates that domain preparation is taking place in a domain in a different forest.
This parameter is not required if the domain being enabled is in the same forest as the computer where the command is being run.

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

### -Domain

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Fully qualified domain name (FQDN) of the domain where domain preparation is to take place (for example, -Domain asia.litwareinc.com).
If this parameter is not included, domain preparation will take place on the local domain.

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

### -DomainController

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables administrators to specify the FQDN of the domain controller to be used when running the Enable-CsAdDomain cmdlet.
If not specified, the cmdlet will use the first available domain controller.

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

### -Force

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Suppresses the display of any non-fatal error message that might arise when running the command.

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

### -GlobalCatalog

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

FQDN of a global catalog server in your domain.
This parameter is not required if you are running the Enable-CsAdDomain cmdlet on a computer with an account in your domain.

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

### -GlobalSettingsDomainController

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

FQDN of a domain controller where global settings are stored.
If global settings are stored in the System container in Active Directory Domain Services, then this parameter must point to the root domain controller.
If global settings are stored in the Configuration container then any domain controller can be used and this parameter can be omitted.

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

### -Report

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Enables you to specify a file path for the log file created when the cmdlet runs.
For example:

`-Report "C:\Logs\DomainPrep.html"`

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipPrepareCheck

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

If set to True ($True), then the Enable-CsAdDomain cmdlet will skip its initial preparation check.

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

### None

## OUTPUTS

### None


## NOTES


## RELATED LINKS

[Disable-CsAdDomain](Disable-CsAdDomain.md)

[Get-CsAdDomain](Get-CsAdDomain.md)

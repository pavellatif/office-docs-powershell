---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/new-csconferencingconfiguration
schema: 2.0.0
---

# New-CsConferencingConfiguration

## SYNOPSIS

Creates a new collection of conference configuration settings.
Conference settings determine such things as the maximum-allowed size for conference content and handouts, the content grace period (that is, the amount of time content will be stored before being deleted), and the URLs for the internal and external downloads of the supported client.
This cmdlet was introduced in Lync Server.



## SYNTAX

```
New-CsConferencingConfiguration [-Identity] <XdsIdentity> [-ClientAppSharingPort <UInt16>]
 [-ClientAppSharingPortRange <UInt32>] [-ClientAudioPort <UInt16>] [-ClientAudioPortRange <UInt32>]
 [-ClientFileTransferPort <UInt16>] [-ClientFileTransferPortRange <UInt32>] [-ClientMediaPort <UInt16>]
 [-ClientMediaPortRange <UInt32>] [-ClientMediaPortRangeEnabled <Boolean>] [-ClientSipDynamicPort <UInt16>]
 [-ClientSipDynamicPortRange <UInt32>] [-ClientVideoPort <UInt16>] [-ClientVideoPortRange <UInt32>]
 [-ConsoleDownloadExternalUrl <String>] [-ConsoleDownloadInternalUrl <String>] [-ContentGracePeriod <TimeSpan>]
 [-HelpdeskExternalUrl <String>] [-HelpdeskInternalUrl <String>] [-MaxBandwidthPerAppSharingServiceMb <UInt64>]
 [-MaxContentStorageMb <UInt16>] [-Organization <String>] [-InMemory] [-Force] [-WhatIf] [-Confirm]
 [-MaxUploadFileSizeMb <UInt16>] [-CloudPollServicePrimaryUrl <String>]
 [-CloudPollServiceSecondaryUrl <String>] [<CommonParameters>]
```

## DESCRIPTION

For conferences, management and administration is split between two sets of cmdlets.
If you want to manage the things users can and cannot do (for example, can users invite anonymous participants to join a conference, are users allowed to offer application sharing in a conference, or are users allowed to transfer files within a conference), then you need to use the CsConferencingPolicy cmdlets.

Administrators also need to manage the Web Conferencing service.
For example, administrators need to be able to do such things as specify the maximum amount of content storage allotted to a single conference and to specify the grace period before that conference content is automatically deleted.
They also need to be able to specify the ports used for activities such as application sharing and file transfer.

These latter activities can be managed by using the CsConferencingConfiguration cmdlets.
These cmdlets enable you to manage the actual servers themselves.
The CsConferencingConfiguration cmdlets (which can be applied to the global, the site, and the service scopes) aren't used to specify whether or not a user can share applications during a conference; if application sharing is allowed, however, these cmdlets enable you to indicate which ports should be used for that activity.
Likewise, the cmdlets enable you to specify such things as storage limits and expiration periods, as well as pointers to internal and external URLs where users can obtain conferencing help and resources.

When you install Skype for Business Server, the system provides you with a single collection of conferencing configuration settings (the global collection).
If you need to create custom settings for a site or service, you can do so using the New-CsConferencingConfiguration cmdlet.
Note that new settings can be applied only at the site or service scope; you cannot create a new global collection of conferencing configuration settings.
In addition, no site or service can host more than one collection of settings.
If you try to create new settings for the Redmond site and the Redmond site already hosts a collection of conferencing configuration settings, then your command will fail.



## EXAMPLES

### EXAMPLE 1
```

New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

The command shown in Example 1 creates a new collection of conferencing configuration settings for the Redmond site (site:Redmond).
In this example, one additional parameter is included (Organization) which is used to set the value of the Organization property to Litwareinc.
Note that this command will fail if the Redmond site already has a collection of conferencing configuration settings.
That's because you can have only one such collection per site.

### EXAMPLE 2
```

$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory

$x.Organization = "Litwareinc"

Set-CsConferencingConfiguration -Instance $x
```

In Example 2, a new collection of conferencing configuration settings is initially created in memory only; these virtual settings are only later applied to the Redmond site.
To do this, the first command in the example uses the New-CsConferencingConfiguration cmdlet to create a new, in-memory collection of settings stored in the variable $x; the InMemory parameter specifies that the collection should be created in memory rather than immediately applied to the Redmond site.

After the collection has been created, the second command sets the value of the Organization property to Litwareinc.
Finally, the third command uses the Set-CsConferencingConfiguration cmdlet to actually apply the new settings to the Redmond site.
(This command will fail if conferencing configuration settings have already been applied to site:Redmond.) If you do not call the Set-CsConferencingConfiguration cmdlet the new settings will never take effect.
Instead, they will disappear as soon as you end your Windows PowerShell session or delete the variable $x.


## PARAMETERS

### -ClientAppSharingPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for application sharing.
The ClientAppSharingPort must be a value port number between 1024 and 65535, inclusive.
The default value is 5350.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientAppSharingPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for application sharing.
(The default value is 40.) To determine the actual ports used for application sharing, use this value and the ClientAppSharingPort value.
For example, if ClientAppSharingPort is set to 5350 and ClientAppSharingPortRange is set to 3, then the following 3 ports are available for application sharing: 5350; 5351; 5352.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientAudioPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for client audio.
The ClientAudioPort must be a value port number between 1024 and 65535, inclusive.
The default value is 5350.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientAudioPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for client audio.
(The default value is 40.) To determine the actual ports used for client audio, use this value and the ClientAudioPort value.
For example, if ClientAudioPort is set to 5350 and ClientAudioPortRange is set to 3, then the following 3 ports are available for client audio: 5350; 5351; 5352.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientFileTransferPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for file transfers.
The ClientFileTransferPort must be a value port number between 1024 and 65535, inclusive.
The default value is 5350.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientFileTransferPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for file transfers.
(The default value is 40.) To determine the actual ports used for file transfers, use this value and the ClientFileTransferPort value.
For example, if ClientFileTransferPort is set to 5350 and ClientFileTransferPortRange is set to 3, then the following three ports are available for file transfers: 5350; 5351; 5352.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientMediaPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for client media.
Use this parameter for Microsoft Office Communicator 2007 R2 clients.
The ClientMediaPort must be a value port number between 1024 and 65535, inclusive.
The default value is 5350.



```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientMediaPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for client media.
(The default value is 40.) Use this parameter for Office Communicator 2007 R2 clients.
To determine the actual ports used for client media, use this value and the ClientMediaPort value.
For example, if ClientMediaPort is set to 5350 and ClientMediaPortRange is set to 3, then the following three ports are available for client media: 5350; 5351; 5352.



```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientMediaPortRangeEnabled

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, clients will use the specified port range for media traffic.
When set to False (the default value) any available port (from port 1024 through port 65535) will be used to accommodate media traffic.

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

### -ClientSipDynamicPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for SIP traffic.
The ClientSipDynamicPort must be a value port number between 1024 and 65535, inclusive.
The default value is 7100.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientSipDynamicPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for SIP traffic.
(The default value is 3.) To determine the actual ports used for SIP traffic, use this value and the ClientSipDynamicPort value.
For example, if ClientSipDynamicPort is set to 7100 and ClientSipDynamicPortRange is set to 3, then the following three ports are available for client media: 7100; 7101; 7102.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientVideoPort

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Represents the starting port number used for client video.
The ClientVideoPort must be a value port number between 1024 and 65535, inclusive.
The default value is 5350.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientVideoPortRange

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the total number of ports available for client video.
(The default value is 40.) To determine the actual ports used for client video, use this value and the ClientVideoPort value.
For example, if ClientVideoPort is set to 5350 and ClientVideoPortRange is set to 3, then the following three ports are available for client video: 5350; 5351; 5352.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudPollServicePrimaryUrl

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is not currently used with Skype for Business Server.

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

### -CloudPollServiceSecondaryUrl

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

This parameter is not currently used with Skype for Business Server.

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

### -ConsoleDownloadExternalUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

URL where external users can download a supported client such as Skype for Business.
Note that this setting applies only to legacy clients (such as Microsoft Office Communicator 2007 R2) that are logging on to a Skype for Business Server 2015 pool.



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

### -ConsoleDownloadInternalUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

URL where internal users can download a supported client such as Skype for Business.
Note that this setting applies only to legacy clients (such as Microsoft Office Communicator 2007 R2) that are logging on to a Skype for Business Server pool.



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

### -ContentGracePeriod

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates how long conference content will remain on the server following the end of a meeting.
The ContentGracePeriod must be specified using the format Days.Hours:Minutes:Seconds.
For example, to set the content grace period to 30 days use this syntax: `-ContentGracePeriod 30.00:00:00.`

The content grace period can be set to any value between 30 minutes (00:30:00) and 180 days (180.00:00:00).
The default value is 15 days (15.00:00:00).



```yaml
Type: TimeSpan
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

Suppresses the display of any non-fatal error message that might occur when running the command.

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

### -HelpdeskExternalUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

URL where external users who click Help during a conference will be directed.

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

### -HelpdeskInternalUrl

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

URL where internal users who click Help during a conference will be directed.

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

### -Identity

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Unique identifier for the collection of conferencing configuration settings to be modified.
To refer to a collection configured at the site scope, use syntax similar to this: `-Identity "site:Redmond".`
To refer to a collection at the service scope, use syntax like the following: `-Identity "service:ConferencingServer:atl-cs-001.litwareinc.com".`
Note the Web Conferencing service is the only service that can host these configuration settings.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMemory

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Creates an object reference without actually committing the object as a permanent change.
If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set-\<cmdlet\>.



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

### -MaxBandwidthPerAppSharingServiceMb

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates the maximum amount of bandwidth (in megabytes) set aside for the Application Sharing Conferencing service.
MaxBandwidthPerAppSharingServiceMb can be set to any integer value between 50 and 100000, inclusive.
The default value is 375 megabytes.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxContentStorageMb

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Maximum amount of file space (in megabytes) allowed for the storage of conference content.
MaxContentStorageMb can be set to any integer value between 50 and 1024 (1 gigabyte), inclusive.
The default value is 500.



```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxUploadFileSizeMb

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Maximum total size of the files (including handouts and PowerPoint slides) that can be used in a given conference.
This setting is typically used when conference content is being archived in Microsoft Exchange Server: by setting a maximum upload file size you can ensure that the content used in the conference (and thus the content which must be archived) does not exceed the maximum file size configured for Microsoft Exchange.
The default value is 500 megabytes.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Organization

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Name of the organization hosting the conference.

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
The New-CsConferencingConfiguration cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConfSettings
The New-CsConferencingConfiguration cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConfSettings object.

## NOTES

## RELATED LINKS

[Get-CsConferencingConfiguration](Get-CsConferencingConfiguration.md)

[Remove-CsConferencingConfiguration](Remove-CsConferencingConfiguration.md)

[Set-CsConferencingConfiguration](Set-CsConferencingConfiguration.md)

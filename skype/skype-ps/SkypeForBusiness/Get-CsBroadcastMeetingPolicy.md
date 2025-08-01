---
applicable: Skype for Business Online
author: tomkau
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
Locale: en-US
manager: bulenteg
Module Name: SkypeForBusiness
ms.author: tomkau
ms.reviewer: williamlooney
online version: https://learn.microsoft.com/powershell/module/skype/get-csbroadcastmeetingpolicy
schema: 2.0.0
title: Get-CsBroadcastMeetingPolicy
---

# Get-CsBroadcastMeetingPolicy

## SYNOPSIS
Use the Get-CsBroadcastMeetingPolicy cmdlet to retrieve the predefined broadcast meeting policies and their settings.

## SYNTAX

### Identity (Default)
```
Get-CsBroadcastMeetingPolicy [-Tenant <Guid>] [[-Identity] <XdsIdentity>] [-LocalStore] [<CommonParameters>]
```

### Filter
```
Get-CsBroadcastMeetingPolicy [-Tenant <Guid>] [-Filter <String>] [-LocalStore] [<CommonParameters>]
```

## DESCRIPTION
Broadcast meeting functionality is managed by broadcast meeting configurations at the tenant level, and broadcast meeting policies at the user level.
Broadcast meeting policies are predefined in Skype for Business.
The defined settings for each policy can be displayed by using the Get-CsBroadcastMeetingPolicy cmdlet with no parameters as in Example 1.
The output will be similar to the listing at the end of this section.
New policies can't be created, and existing policies can't be modified.
They can only be granted, or assigned to users.
For more information, see Grant-CsBroadcastMeetingPolicy.

Identity : Global

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : True

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyDefault

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : True

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyDisabled

AllowBroadcastMeeting : False

AllowOpenBroadcastMeeting : False

AllowSocialStreamIntegration : False

AllowBroadcastMeetingRecording : False

AllowAnonymousBroadcastMeeting : False

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyAllEnabled

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : True

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyAnonymousDisabled

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : False

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyRecordingDisabled

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : False

AllowAnonymousBroadcastMeeting : True

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyAnonymousDisabledAndRecordingNotEnforced

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : False

BroadcastMeetingRecordingEnforced : False

Identity : Tag:BroadcastMeetingPolicyAnonymousDisabledAndRecordingEnforced

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : True

AllowAnonymousBroadcastMeeting : False

BroadcastMeetingRecordingEnforced : True

Identity : Tag:BroadcastMeetingPolicyAnonymousAndRecordingDisabled

AllowBroadcastMeeting : True

AllowOpenBroadcastMeeting : True

AllowSocialStreamIntegration : True

AllowBroadcastMeetingRecording : False

AllowAnonymousBroadcastMeeting : False

BroadcastMeetingRecordingEnforced : False


## EXAMPLES

### Example 1
```
Get-CsBroadcastMeetingPolicy
```

This example lists all the pre-defined policy configurations for your organization.
See detailed description for more information.


## PARAMETERS

### -Filter

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

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

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalStore

> Applicable: Skype for Business Online

Retrieves the information from the local replica of the Central Management store, rather than the Central Management store itself.

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

### -Tenant

> Applicable: Skype for Business Online

This parameter is reserved for internal Microsoft use.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

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

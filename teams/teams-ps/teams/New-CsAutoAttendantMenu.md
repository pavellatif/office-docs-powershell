---
external help file: Microsoft.Rtc.Management.Hosted.dll-help.xml
online version: https://learn.microsoft.com/powershell/module/teams/new-csautoattendantmenu
applicable: Microsoft Teams
title: New-CsAutoAttendantMenu
schema: 2.0.0
manager: bulenteg
author: tomkau
ms.author: tomkau
ms.reviewer: williamlooney
---

# New-CsAutoAttendantMenu

## SYNOPSIS
The New-CsAutoAttendantMenu cmdlet creates a new menu.

## SYNTAX

```
New-CsAutoAttendantMenu -Name <String> [-MenuOptions <List>] [-Prompts <List>] [-EnableDialByName] [-Tenant <Guid>] [-DirectorySearchMethod] [<CommonParameters>]
```

## DESCRIPTION
The New-CsAutoAttendantMenu cmdlet creates a new menu for the Auto Attendant (AA) service. The OAA service uses menus to provide callers with choices, and then takes action based on the selection.

## EXAMPLES

### -------------------------- Example 1 --------------------------
```
$menuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To reach your party by name, enter it now, followed by the pound sign."
$menu = New-CsAutoAttendantMenu -Name "Default Menu" -Prompts @($menuPrompt) -EnableDialByName -DirectorySearchMethod ByExtension
```

This example creates a new menu that allows the caller to reach a target by name, and also defines the Directory Search Method to Dial By Extension.

### -------------------------- Example 2 --------------------------
```
$menuOptionZero = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
$menuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To reach your party by name, enter it now, followed by the pound sign. For operator, press zero."
$menu = New-CsAutoAttendantMenu -Name "Default Menu" -Prompts @($menuPrompt) -MenuOptions @($menuOptionZero) -EnableDialByName -DirectorySearchMethod ByName
```

This example creates a new menu that allows the caller to reach a target by name or the operator by pressing the 0 key, and also defines the Directory Search Method to Dial By Name.

## PARAMETERS

### -Name
The Name parameter represents a friendly name for the menu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MenuOptions
The MenuOptions parameter is a list of menu options for this menu. These menu options specify what action to take when the user sends a particular input.

You can create menu options by using the New-CsAutoAttendantMenuOption cmdlet.

```yaml
Type: System.Collections.Generic.List
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prompts
The Prompts parameter reflects the prompts to play when the menu is activated.

You can create prompts by using the [`New-CsAutoAttendantPrompt`](https://learn.microsoft.com/powershell/module/teams/new-csautoattendantprompt) cmdlet.

> [!NOTE]
> If Mainline Attendant is enabled, only TTS prompts are supported.

```yaml
Type: Object
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDialByName
The EnableDialByName parameter lets users do a directory search by recipient name and get transferred to the party.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectorySearchMethod
The DirectorySearchMethod parameter lets you define the type of Directory Search Method for the Auto Attendant menu, for more information, see [Set up a Cloud auto attendant](https://learn.microsoft.com/MicrosoftTeams/create-a-phone-system-auto-attendant?WT.mc_id=TeamsAdminCenterCSH)

Possible values are

- None
- ByName
- ByExtension

```yaml
Type: Microsoft.Rtc.Management.Hosted.OAA.Models.DirectorySearchMethod
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:
applicable: Microsoft Teams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Rtc.Management.Hosted.OAA.Models.Menu

## NOTES

## RELATED LINKS

[New-CsAutoAttendantMenuOption](https://learn.microsoft.com/powershell/module/teams/new-csautoattendantmenuoption)
[New-CsAutoAttendantPrompt](https://learn.microsoft.com/powershell/module/teams/new-csautoattendantmenuoption)

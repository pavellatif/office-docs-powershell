---
applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/test-csexstoragenotification
schema: 2.0.0
title: Test-CsExStorageNotification
---

# Test-CsExStorageNotification

## SYNOPSIS
Verifies that the Skype for Business Server Storage Service running on a Front End server can subscribe to the Exchange mailbox notification service.
This is done by having the cmdlet subscribe to the service, create an item, verify that notification of the new item is received, and then, optionally, delete that item unsubscribe from the service.
This cmdlet was introduced in Lync Server 2013.


## SYNTAX

```
Test-CsExStorageNotification -SipUri <String> [-Binding <String>] [-DeleteItem] [-Force]
 [-HostNameStorageService <String>] [<CommonParameters>]
```

## DESCRIPTION
The `Test-CsExStorageNotification` cmdlet is used to verify that the Exchange notification service is able to notify Skype for Business Server any time updates are made to a user's Contact List.
This cmdlet is valid only if you are using the unified contact store.

Skype for Business Server Control Panel: The functions carried out by the `Test-CsExStorageNotification` cmdlet are not available in the Skype for Business Server Control Panel.


## EXAMPLES

### Example 1
```
Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"
```

The command shown in Example 1 tests to see if the Skype for Business Server Storage Service can connect to the Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.
In this example, NetNamedPipe is used as the WCF binding.


## PARAMETERS

### -Binding

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Windows Communication Foundation (WCF) binding.
A WCF binding determines the transport, encoding, and protocol details required for clients and services to communicate with each other.
valid values are:

* NetNamedPipe
* NetTCP

```yaml
Type: String
Parameter Sets: (All)
Aliases: b

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeleteItem

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When present, the test item will be deleted from the Exchange mailbox at the end of the text.

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

### -Force

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

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

### -HostNameStorageService

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Fully qualified domain name of the server where the Skype for Business Server Storage Service is running.
This parameter is required if the Binding is set to NetTCP.


```yaml
Type: String
Parameter Sets: (All)
Aliases: h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SipUri

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

SIP address of the Exchange Server mailbox where the test item should be created.

```yaml
Type: String
Parameter Sets: (All)
Aliases: s

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
The `Test-CsExStorageNotification` cmdlet does not accept pipelined input.

## OUTPUTS

### Microsoft.Rtc.Management.ResourceData
The `Test-CsExStorageNotification` cmdlet returns instances of the Microsoft.Rtc.Management.ResourceData object.

## NOTES

## RELATED LINKS

[Test-CsExStorageConnectivity](Test-CsExStorageConnectivity.md)

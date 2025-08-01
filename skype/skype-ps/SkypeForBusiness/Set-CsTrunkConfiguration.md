---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019
author: hirenshah1
external help file: Microsoft.Rtc.Management.dll-help.xml
Locale: en-US
manager: rogupta
Module Name: SkypeForBusiness
ms.author: hirshah
online version: https://learn.microsoft.com/powershell/module/skype/set-cstrunkconfiguration
schema: 2.0.0
title: Set-CsTrunkConfiguration
---

# Set-CsTrunkConfiguration

## SYNOPSIS
Modifies an existing trunk configuration that describes the settings for a trunking peer entity such as a public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider.
This cmdlet was introduced in Lync Server 2010.


## SYNTAX

### Identity
```
Set-CsTrunkConfiguration [[-Identity] <XdsIdentity>] [-ConcentratedTopology <Boolean>] [-Description <String>]
 [-EnableBypass <Boolean>] [-EnableMobileTrunkSupport <Boolean>] [-EnablePIDFLOSupport <Boolean>]
 [-EnableReferSupport <Boolean>] [-EnableSessionTimer <Boolean>] [-EnableSignalBoost <Boolean>]
 [-MaxEarlyDialogs <UInt32>] [-OutboundTranslationRulesList <PSListModifier>] [-RemovePlusFromUri <Boolean>]
 [-RTCPActiveCalls <Boolean>] [-RTCPCallsOnHold <Boolean>]
 [-SipResponseCodeTranslationRulesList <PSListModifier>] [-SRTPMode <SRTPMode>] [-Force] [-WhatIf] [-Confirm]
 [-Enable3pccRefer <Boolean>] [-EnableFastFailoverTimer <Boolean>] [-EnableOnlineVoice <Boolean>]
 [-EnableRTPLatching <Boolean>] [-ForwardCallHistory <Boolean>] [-ForwardPAI <Boolean>] [-ForwardAnonymousCallGatewayPAI <Boolean>]
 [-OutboundCallingNumberTranslationRulesList <PSListModifier>] [-PstnUsages <PSListModifier>]
 [-EnableLocationRestriction <Boolean>] [-NetworkSiteID <String>] [AcceptGatewayPAIForOutboundCalls] [<CommonParameters>]
```

### Instance
```
Set-CsTrunkConfiguration [-Instance <PSObject>] [-ConcentratedTopology <Boolean>] [-Description <String>]
 [-EnableBypass <Boolean>] [-EnableMobileTrunkSupport <Boolean>] [-EnablePIDFLOSupport <Boolean>]
 [-EnableReferSupport <Boolean>] [-EnableSessionTimer <Boolean>] [-EnableSignalBoost <Boolean>]
 [-MaxEarlyDialogs <UInt32>] [-OutboundTranslationRulesList <PSListModifier>] [-RemovePlusFromUri <Boolean>]
 [-RTCPActiveCalls <Boolean>] [-RTCPCallsOnHold <Boolean>]
 [-SipResponseCodeTranslationRulesList <PSListModifier>] [-SRTPMode <SRTPMode>] [-Force] [-WhatIf] [-Confirm]
 [-Enable3pccRefer <Boolean>] [-EnableFastFailoverTimer <Boolean>] [-EnableOnlineVoice <Boolean>]
 [-EnableRTPLatching <Boolean>] [-ForwardCallHistory <Boolean>] [-ForwardPAI <Boolean>] [-ForwardAnonymousCallGatewayPAI <Boolean>]
 [-OutboundCallingNumberTranslationRulesList <PSListModifier>] [-PstnUsages <PSListModifier>]
 [-EnableLocationRestriction <Boolean>] [-NetworkSiteID <String>] [AcceptGatewayPAIForOutboundCalls] [<CommonParameters>]
```

## DESCRIPTION
Use this cmdlet to modify a trunking configuration applicable to PSTN gateway entities.
Each configuration contains specific settings for a trunking peer entity such as a PSTN gateway, IP-PBX, or SBC at the service provider.
These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.


## EXAMPLES

### Example 1
```
Set-CsTrunkConfiguration -Identity site:Redmond -EnableBypass $True
```

This example modifies a trunk configuration with the Identity site:Redmond to enable media bypass.
Media bypass is enabled by assigning the value $True to the EnableBypass parameter.
The remaining properties for this configuration will retain their existing values.


### Example 2
```
Set-CsOutboundTranslationRule -Identity site:Redmond/OTR1 -Translation '$1'
```

This example modifies an outbound translation rule defined for the trunk configuration with the Identity site:Redmond.
Notice that we don't actually make a call to the `Set-CsTrunkConfiguration` cmdlet to make this change.
Changes made using the `Set-CsOutboundTranslationRule` cmdlet will be automatically reflected in the trunk configuration with an Identity matching the scope portion of the Identity of the outbound translation rule.


### Example 3
```
Get-CsTrunkConfiguration -Filter site:* | Set-CsTrunkConfiguration -SRTPMode "Optional"
```

Example 3 sets the SRTPMode for all trunk configurations defined at the site scope to Optional.
The first part of the command is a call to the `Get-CsTrunkConfiguration` cmdlet that uses the Filter parameter to retrieve all trunk configurations with an Identity beginning with site:, meaning all trunk configurations defined at the site level.
This collection of configurations is then piped to the `Set-CsTrunkConfiguration` cmdlet, which sets the SRTPMode property of each to Optional.


### EXAMPLE 4
```
Set-CsTrunkConfiguration -Identity site:Redmond -EnablePIDFLOSupport $True
```

Example 4 modifies a trunk configuration with the Identity site:Redmond to enable PIDF-LO support.
By default the EnablePIDFLOSupport parameter is False.
In this example we've set the value to True to enable location support for emergency calls.
You must set EnablePIDFLOSupport to True in order for location information to be sent to the trunk by the outbound routing application.


## PARAMETERS

### -AcceptGatewayPAIForOutboundCalls

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Set this parameter to True ($true) to modify the trunk configuration to display forwarded number for different trunks.
This parameter was introduced in the January 2019 cumulative update, for more information see [Incorrect caller ID is shown on the Skype for Business client in a call-forwarding scenario](https://support.microsoft.com/help/4458692/incorrect-caller-id-shown-on-the-skype-for-business-client-in-a-call)

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```


### -ConcentratedTopology

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The value of this parameter determines whether there is a well-known media termination point.
(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.) Set this value to False if the trunk does not have a well-known media termination point.

Default: True

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

### -Description

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

A string describing the purpose of the trunk configuration.

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

### -Enable3pccRefer

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.
3pcc is also known as "third party control" and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).
The REFER method is a standard SIP method which indicates that the recipient should contact a third-party by using information supplied by the sender.
The default value is False ($False).

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

### -EnableBypass

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The value of this parameter determines whether media bypass is enabled for this trunk.
Set this value to True to enable bypass.
Note that in order for the media bypass to work successfully, certain capabilities must be supported by PSTN gateways, SBCs, and PBXs, including:

- The ability to receive forked responses to an Invite.
- Skype for Business clients and the media termination point must be able to communicate directly without going through a Mediation Server.
- The gateway subnet must be defined as being at the same site as the client's subnet or, if at a different site, the sites must not be separated by WAN links with constrained bandwidth.

Media bypass can be enabled only under the following circumstances:

- The ConcentratedTopology parameter is set to True
- The EnableReferSupport parameter is set to False and RTCPActiveCalls and RTCPCallsOnHold are set to False, or EnableReferSupport is set to True

Note that if EnableBypass is True and EnableReferSupport is False, bypass calls that are subsequently transferred will become non-bypass.

For media bypass to work for a particular trunk, it needs to be enabled globally and also for the trunk in question.
Use the `New-CsNetworkMediaBypassConfiguration` cmdlet to enable media bypass globally.

Default: False


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

### -EnableFastFailoverTimer

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When set to True, outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.
In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.

The default value is True.

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

### -EnableLocationRestriction

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

When set to True, location-based voice routing will be enabled for calls passing through the SIP trunks managed by the specified collection of SIP trunk configuration settings.
With location-based voice routing, the locations of both the user making the call and the user receiving the call are taken into account when calls are routed.
If this property is set to True (the default value is False) then you should also set the NetworkSiteId property.

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

### -EnableMobileTrunkSupport

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Defines whether the service provider is a mobile carrier.

Default: False

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

### -EnableOnlineVoice

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether the SIP trunks support online voice.
With online voice, users have an on-premises Lync Server account but have their voicemail hosted by Skype for Business Online.
The default value is False ($False).


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

### -EnablePIDFLOSupport

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Defines whether to route emergency calls with Presence Information Data Format Location Object (PIDF-LO) through the defined gateway.
Set this parameter to True if emergency calls are to be routed to a certified emergency services provider.
(The location will be transmitted with the call.)

Default: False

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

### -EnableReferSupport

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Defines whether this trunk supports receiving Refer requests from the Mediation Server.

Media bypass can be enabled only under the following circumstances:

- The ConcentratedTopology parameter is set to True
- The EnableReferSupport parameter is set to False and RTCPActiveCalls and RTCPCallsOnHold are set to False, or EnableReferSupport is set to True

Note that if EnableBypass is True and EnableReferSupport is False, bypass calls that are subsequently transferred will become non-bypass.

Default: True

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

### -EnableRTPLatching

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether or not the SIP trunks support RTP latching.
RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.
The default value is False ($False).

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

### -EnableSessionTimer

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Specifies whether the session timer is enabled.
Session timers are used to determine whether a particular session is still active.

Note that even if this parameter is set to False, session timers can be applicable if the remote connection has session timer enabled.
In such a case, the Mediation Server will reply to session timer probes from the remote entity.

Default: False

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

### -EnableSignalBoost

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

When this parameter is set to True the PSTN gateway, IP-PBX or SBC at the service provider will boost the audio volume in voice streams that are sent to the Mediation Server or Skype for Business Server clients.
If this value is set to False, audio will be boosted either at the Mediation Server (for non-bypass calls) or in Skype for Business Server clients (for bypass calls).

Default: False


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

### -ForwardAnonymousCallGatewayPAI

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

If an anonymous call is forwarded to an outgoing PSTN call, this parameter indicates whether the incoming P-Asserted-Identity (PAI) header at the Gateway call will be preserved in the PSTN call. The default value is **False** ($False).

**Notes:**
- `EnablePAIPAssthrough` is deprecated in favor of `ForwardAnonymousCallGatewayPAI`. This change is made by installing KB5016483.
- When `ForwardAnonymousCallGatewayPAI` is used, `ForwardPAI` must be set to **True**.

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

### -ForwardCallHistory

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether call history information will be forwarded through the trunk.
The default value is False ($False).

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

### -ForwardPAI

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.
The PAI header provides a way to verify the identity of the caller.
The default value is False ($False).

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

### -Identity

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

A unique identifier that includes the scope of the trunk configuration.
Trunk configurations can exist at the Global scope, the Site scope, or at the Service scope for a PSTN Gateway service.
For example, site:Redmond (for site) or PstnGateway:Redmond.litwareinc.com (for service).

```yaml
Type: XdsIdentity
Parameter Sets: Identity
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.

This parameter requires an object of type Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration, which can be retrieved by calling the `Get-CsTrunkConfiguration` cmdlet.

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

### -MaxEarlyDialogs

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.

Default: 20

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

### -NetworkSiteID

> Applicable: Skype for Business Server 2015, Skype for Business Server 2019

Site ID of the network site associated with the collection of trunk configuration settings.
If the EnableLocationRestriction property is set to True then location-based voice routing through this trunk will be managed by using the settings configured for the specified site.
Network site IDs can be retrieved by using this command:

`Get-CsNetworkSite | Select NetworkSiteID`

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

### -OutboundCallingNumberTranslationRulesList

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Collection of outbound calling number translation rules assigned to the trunk.
You can retrieve information about the available rules by running this command:

`Get-CsOutboundCallingNumberTranslationRule`

```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutboundTranslationRulesList

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

A collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).

While this list and these rules can be modified directly with this cmdlet, we recommend that you modify the outbound translation rules with the `Set-CsOutboundTranslationRule` cmdlet.
The `Set-CsOutboundTranslationRule` cmdlet will modify the rule and these modifications will be automatically reflected in the trunk configuration.
To modify the trunk configuration by adding a new outbound translation rule, call the `New-CsOutboundTranslationRule` cmdlet; the new rule will be added to the trunk configuration with the matching scope.


```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PstnUsages

> Applicable: Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Collection of PSTN usages assigned to the trunk.
You can retrieve information about the available usages by running this command:

`Get-CsPstnUsage`

```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePlusFromUri

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

Setting this parameter to True will cause the Mediation Server to remove leading plus signs (+) from Uniform Resources Identifiers (URIs) before sending them on to the service provider.

Default: False

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

### -RTCPActiveCalls

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

This parameter determines whether RTCP packets are sent from the PSTN gateway, IP-PBX or SBC at the service provider for active calls.
An active call in this context is a call where media is allowed to flow in at least one direction.
If RTCPActiveCalls is set to True, the Mediation Server or Skype for Business Server client can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.

Note that disabling the checks for received RTCP media for active calls in Skype for Business Server elements removes an important safeguard for detecting a dropped peer and should be done only if necessary.

Default: True


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

### -RTCPCallsOnHold

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.
If Music on Hold is enabled at either the Skype for Business Server client or the trunk, the call will be considered to be active and this property will be ignored.
In these circumstances use the RTCPActiveCalls parameter.

Note that disabling the checks for received RTCP media for active calls in Skype for Business Server elements removes an important safeguard for detecting a dropped peer and should be done only if necessary.

Default: True


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

### -SipResponseCodeTranslationRulesList

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

A list of SIP response code translation rules that apply to response codes received from a PSTN gateway, IP-PBX or SBC at the service provider.
These rules allow the administrator to map SIP response codes with values between 400 and 699 received over a trunk to new values more consistent with Skype for Business Server.

You can create this list and corresponding rules directly with this cmdlet.
However, we recommend that you create the SIP response code translation rules by calling the `New-CsSipResponseCodeTranslationRule` cmdlet.
That cmdlet will create the rule and assign it to the trunk configuration with the matching scope.


```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SRTPMode

> Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015, Skype for Business Server 2019

The value of this parameter determines the level of support for SRTP to protect media traffic between the Mediation Server and the PSTN gateway, IP-PBX, or SBC at the service provider.
For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.
Media configuration is set by using the `New-CsMediaConfiguration` cmdlet and the `Set-CsMediaConfiguration` cmdlet.

Valid values:

- Required: SRTP encryption must be used.
- Optional: SRTP will be used if the service provider supports it.
- NotSupported: SRTP encryption is not supported and therefore will not be used.

Note: SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).
If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to NotSupported.

Default: Required


```yaml
Type: SRTPMode
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

### Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration

Accepts pipelined input of trunk configuration objects.

## OUTPUTS

### None
This cmdlet does not return a value; it modifies an object of type Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TrunkConfiguration.

## NOTES

## RELATED LINKS

[New-CsTrunkConfiguration](New-CsTrunkConfiguration.md)

[Remove-CsTrunkConfiguration](Remove-CsTrunkConfiguration.md)

[Get-CsTrunkConfiguration](Get-CsTrunkConfiguration.md)

[Test-CsTrunkConfiguration](Test-CsTrunkConfiguration.md)

[New-CsOutboundTranslationRule](New-CsOutboundTranslationRule.md)

[Set-CsOutboundTranslationRule](Set-CsOutboundTranslationRule.md)

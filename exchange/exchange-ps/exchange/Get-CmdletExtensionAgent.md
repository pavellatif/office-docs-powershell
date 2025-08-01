---
external help file: Microsoft.Exchange.ProvisioningAndMigration-Help.xml
online version: https://learn.microsoft.com/powershell/module/exchange/get-cmdletextensionagent
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019
title: Get-CmdletExtensionAgent
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# Get-CmdletExtensionAgent

## SYNOPSIS
This cmdlet is available only in on-premises Exchange.

Use the Get-CmdletExtensionAgent cmdlet to view cmdlet extension agents.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://learn.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

### Filters
```
Get-CmdletExtensionAgent [-Assembly <String>]
 [-Enabled <Boolean>]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

### Identity
```
Get-CmdletExtensionAgent [[-Identity] <CmdletExtensionAgentIdParameter>]
 [-DomainController <Fqdn>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet extension agents are used by Exchange cmdlets in Exchange Server 2010 and later. Cmdlets provided by other Microsoft or non-Microsoft products can't use cmdlet extension agents.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://learn.microsoft.com/powershell/exchange/find-exchange-cmdlet-permissions).

## EXAMPLES

### Example 1
```powershell
Get-CmdletExtensionAgent | Format-Table -Auto Name,Enabled,Priority
```

This example displays a summary list of all the cmdlet extension agents in the organization.

### Example 2
```powershell
Get-CmdletExtensionAgent "Mailbox Creation Time Agent"
```

This example displays detailed information for the Exchange cmdlet extension agent named Mailbox Creation Time Agent.

## PARAMETERS

### -Identity
The Identity parameter specifies the name of the cmdlet extension agent that you want to view. You can use any value that uniquely identifies the agent. For example:

- Name
- Distinguished name (DN)
- GUID

```yaml
Type: CmdletExtensionAgentIdParameter
Parameter Sets: Identity
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

Required: False
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -Assembly
The Assembly parameter filters the results by the specified Assembly property value. The value for the built-in Exchange cmdlet extension agents is Microsoft.Exchange.ProvisioningAgent.dll.

```yaml
Type: String
Parameter Sets: Filters
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
The Enabled parameter filters the results by enabled or disabled cmdlet extension agents. Valid values are:

- $true: Only enabled agents are included in the results.
- $false: Only disabled agents are included in the results.

If you don't use this parameter, enabled and disabled agents are included in the results.

```yaml
Type: Boolean
Parameter Sets: Filters
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016, Exchange Server 2019

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

### Input types
To see the input types that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

### Output types
To see the return types, which are also known as output types, that this cmdlet accepts, see [Cmdlet Input and Output Types](https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS

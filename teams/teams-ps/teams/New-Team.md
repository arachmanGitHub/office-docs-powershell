---
external help file: Microsoft.TeamsCmdlets.PowerShell.Custom.dll-Help.xml
Module Name: MicrosoftTeams
applicable: Microsoft Teams
title: New-Team
online version:
schema: 2.0.0
---

# New-Team

## SYNOPSIS
This cmdlet lets you provision a new Team for use in Microsoft Teams and will create an O365 Unified Group to back the team.  Groups created through teams cmdlets, APIs, or clients will not show up in Outlook by default.  If you want these groups to appear in Outlook clients, you can use the Set-UnifiedGroup (https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/set-unifiedgroup?view=exchange-ps) cmdlet in the Exchange Powershell Module to set the parameter HiddenFromExchangeClients to $false. 

Note: This cmdlet is currently in Beta and functionality may change.

## SYNTAX

```
New-Team [-Group <String>] [-DisplayName <String>] [-Description <String>] [-Alias <String>]
 [-Classification <String>] [-AccessType <String>] [-AddCreatorAsMember <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
Creates a new team with user specified settings, and returns a Group object with a GroupID property.

## EXAMPLES

### Example 1
```
New-Team -DisplayName "Tech Reads"
```

### Example 2
```
New-Team -DisplayName "Tech Reads" -Description "Team to post technical articles and blogs" -AccessType Public
```

### Example 3
```
Connect-MicrosoftTeams -AccountId myaccount@example.com
$group = New-Team -alias "TestTeam" -displayname "Test Teams" -AccessType "private"
Add-TeamUser -GroupId $group.GroupId -User "fred@example.com"
Add-TeamUser -GroupId $group.GroupId -User "john@example.com"
Add-TeamUser -GroupId $group.GroupId -User "wilma@example.com"
New-TeamChannel -GroupId $group.GroupId -DisplayName "Q4 planning"
New-TeamChannel -GroupId $group.GroupId -DisplayName "Exec status"
New-TeamChannel -GroupId $group.GroupId -DisplayName "Contracts"
Set-TeamFunSettings -GroupId $group.GroupId -AllowCustomMemes true
```

## PARAMETERS

### -AccessType
Team access type.
Valid values are "Private" and "Public".
Default is "Private".
(This parameter has the same meaning as -AccessType in New-UnifiedGroup.)

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AddCreatorAsMember
This setting lets you decide if you will be added as a member of the group. 
Because you are automatically an owner of the group, you will always be added as a member to the team.

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

### -Alias
Same as displayName without any spaces.
Team Alias Characters Limit - 64

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Classification
Team classification

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Team description.
Team Description Characters Limit - 1024.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Team display name.
Team Name Characters Limit - 256.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Group
Use this parameter to specify the groupid of a group you would like to convert to a team.
If you use this parameter, do not specify other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### GroupId

## NOTES

## RELATED LINKS

---
external help file: Microsoft.Exchange.RecordsandEdge-Help.xml
applicable: Exchange Server 2016, Office 365 Security & Compliance Center
title: New-ComplianceSearchAction
schema: 2.0.0
monikerRange: "exchserver-ps-2016 || o365scc-ps"
---

# New-ComplianceSearchAction

## SYNOPSIS
This cmdlet is available in on-premises Exchange and in the cloud-based service. Some parameters and settings may be exclusive to one environment or the other.

Use the New-ComplianceSearchAction cmdlet to create actions for compliance searches in Exchange Server 2016 and in the Office 365 Security & Compliance Center.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

## SYNTAX

### Set3
```
New-ComplianceSearchAction [[-SearchName] <String[]>] [-ActionName <String>]
 [-ArchiveFormat <Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst>]
 [-Confirm] [-EnableDedupe <$true | $false>]
 [-ExchangeArchiveFormat <Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst>]
 [-Export] [-FileTypeExclusionsForUnindexedItems <String[]>] [-Force]
 [-Format <Unknown | FxStream | Mime | Msg | BodyText>] [-IncludeCredential]
 [-IncludeSharePointDocumentVersions <$true | $false>] [-JobOptions <Int32>] [-MaxUnindexedSize <Int32>]
 [-NotifyEmail <String>] [-NotifyEmailCC <String>] [-ReferenceActionName <String>] [-Region <String>] [-Report]
 [-RetentionReport] [-RetryOnError]
 [-Scenario <Unknown | General | AnalyzeWithZoom | GenerateReportsOnly | Inventory | RetentionReports | TriagePreview>]
 [-Scope <Unknown | IndexedItemsOnly | UnindexedItemsOnly | BothIndexedAndUnindexedItems>]
 [-ScopeDetails <ComplianceScopeDetail[]>] [-SearchNames <String[]>]
 [-SharePointArchiveFormat <Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst>]
 [-ShareRootPath <String>] [-Version <String>] [-WhatIf] [<CommonParameters>]
```

### Set2
```
New-ComplianceSearchAction [[-SearchName] <String[]>] [-ActionName <String>] [-Confirm] [-Force]
 [-Format <Unknown | FxStream | Mime | Msg | BodyText>] [-IncludeCredential] [-JobOptions <Int32>] [-Preview]
 [-ReferenceActionName <String>] [-Region <String>] [-RetryOnError]
 [-Scenario <Unknown | General | AnalyzeWithZoom | GenerateReportsOnly | Inventory | RetentionReports | TriagePreview>]
 [-SearchNames <String[]>] [-Version <String>] [-WhatIf] [<CommonParameters>]
```

### Set4
```
New-ComplianceSearchAction [[-SearchName] <String[]>] [-ActionName <String>] [-Confirm] [-Force]
 [-Format <Unknown | FxStream | Mime | Msg | BodyText>] [-IncludeCredential] [-JobOptions <Int32>] [-Purge]
 [-PurgeType <Unknown | SoftDelete>] [-ReferenceActionName <String>] [-Region <String>] [-RetryOnError]
 [-Scenario <Unknown | General | AnalyzeWithZoom | GenerateReportsOnly | Inventory | RetentionReports | TriagePreview>]
 [-SearchNames <String[]>] [-Version <String>] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
After you create a compliance search using the New-ComplianceSearch cmdlet and run it using the Start-ComplianceSearch cmdlet, you assign a search action to the search using the New-ComplianceSearchAction cmdlet.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see Find the permissions required to run any Exchange cmdlet (https://technet.microsoft.com/library/mt432940.aspx).

This cmdlet is available in the Mailbox Search role. By default, this role is assigned only to the Discovery Management role group, and not to the Organization Management role group.

You need to be assigned permissions in the Office 365 Security & Compliance Center before you can use this cmdlet. For more information, see Permissions in Office 365 Security & Compliance Center (https://go.microsoft.com/fwlink/p/?LinkId=511920).

## EXAMPLES

### -------------------------- Example 1 --------------------------
```
New-ComplianceSearchAction -SearchName "Project X" -Preview
```

This example creates a preview search action for the compliance search named Project X.

### -------------------------- Example 2 --------------------------
```
New-ComplianceSearchAction -SearchName "Project X" -Export
```

This example creates an export search action for the compliance search named Project X.

### -------------------------- Example 3 --------------------------
```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

This example deletes the search results returned by a compliance search named Remove Phishing Message. Note that unindexed items aren't deleted when you use the Purge parameter.

## PARAMETERS

### -ActionName
The ActionName parameter specifies a name for the compliance search action. You use this parameter only when you specify multiple compliance searches in the SearchName parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ArchiveFormat
The ArchiveFormat parameter specifies how to export Exchange search results. Valid values are:

- PerUserPst: One PST file for each mailbox. This is the default value.

- SinglePst: One PST file that contains all exported messages.

- SingleFolderPst: One PST file with a single root folder for the entire export.

- IndividualMessage: Export each message as a file, using the .msg format.

- SingleZip: One ZIP file that contains all exported messages.

- PerUserZip: One ZIP file for each mailbox.

```yaml
Type: Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: -Confirm:$false.

- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableDedupe
The EnableDedupe parameter eliminates duplication of messages when you export compliance search results. Valid values are:

- $true: Export a single copy of a message if the same message exists in multiple folders or mailboxes.

- $false: Export all copies of a message if the same message exists in multiple folders or mailboxes. This is the default value.

```yaml
Type: $true | $false
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeArchiveFormat
The ExchangeArchiveFormat parameter specifies how to export Exchange search results. Valid values are:

- PerUserPst: One PST file for each mailbox. This is the default value.

- SinglePst: One PST file that contains all exported messages.

- SingleFolderPst: One PST file with a single root folder for the entire export.

- IndividualMessage: Export each message as a file, using the .msg format.

- SingleZip: One ZIP file that contains all exported messages, using the .msg format.

- PerUserZip: One ZIP file for each mailbox.

```yaml
Type: Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Export
The Export switch specifies the action for the compliance search is to export the full set of results that match the search criteria. You don't need to specify a value with this switch.

To only return the information about each detected item in a report, use the Report switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileTypeExclusionsForUnindexedItems
The FileTypeExclusionsForUnindexedItems specifies the file types to exclude because they can't be indexed. You can specify multiple values separated by commas.

```yaml
Type: String[]
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
The Force switch specifies whether to suppress warning or confirmation messages. You can use this switch to run tasks programmatically where prompting for administrative input is inappropriate. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Format
The Format parameter specifies the format of the search results when you use the Export switch. Valid values are:

- FxStream: Export to PST files. This is the only option that's available when you export search results from the Security & Compliance Center.

- Mime: Export to .eml messsage files. This the default value when you use cmdlets to export the search results.

- Message: Export to .msg messsage files.

- BodyText: Export to .txt files.

```yaml
Type: Unknown | FxStream | Mime | Msg | BodyText
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeCredential
The IncludeCredential switch specifies whether to include the credential in the results. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSharePointDocumentVersions
The IncludeSharePointDocumentVersions parameter specifies whether to export previous versions of the document when you use the Export switch. Valid values are:

- $true: Export all versions of the document.

- $false: Export only the current published version of the topic. This is the default value.

```yaml
Type: $true | $false
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobOptions
This parameter is reserved for internal Microsoft use.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxUnindexedSize
The MaxUnindexedSize parameter specifies the maximum size in bytes for unindexed items. A valid value is an integer.

```yaml
Type: Int32
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotifyEmail
The NotifyEmail parameter specifies the email address target for the search results when you use the Export switch.

The recipient you specify is in the To: field of the message.

```yaml
Type: String
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotifyEmailCC
The NotifyEmailCC parameter specifies the email address target for the search results when you use the Export switch.

The recipient you specify is in the Cc: field of the message.

```yaml
Type: String
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Preview
The Preview switch specifies the action for the compliance search is to preview the results that match the search criteria. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set2
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Purge
The Purge switch specifies the action for the compliance search is to remove items that match the search criteria. You don't need to specify a value with this switch.

Note that a maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This action isn't intended to clean up user mailboxes.

Additionally, unindexed items aren't removed from mailboxes when you use this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set4
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PurgeType
The PurgeType parameter specifies how to remove items when the action is Purge.

The valid value for this parameter is SoftDelete, which means the purged items are recoverable by users until the deleted items retention period expires.

```yaml
Type: Unknown | SoftDelete
Parameter Sets: Set4
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReferenceActionName
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Region
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Report
The Report switch specifies the action for the compliance search is to export a report about the results (information about each item instead of the full set of results) that match the search criteria. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionReport
The RetentionReport switch specifies the action for the compliance search is to export a retention report. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetryOnError
The RetryOnError switch specifies whether to retry the action on any items that failed without re-running the entire action all over again. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scenario
The Scenario parameter specifies the scenario type when you use the Export switch. Valid values are:

- AnalyzeWithZoom: Prepare the search results for processing in Office 365 Advanced eDiscovery.

- General: Exports the search results to the local computer. Emails are exported to .pst files. SharePoint and OneDrive for Business documents are exported in their native Office formats.

- GenerateReportsOnly:

- Inventory:

- RetentionReports:

- TriagePreview:

```yaml
Type: Unknown | General | AnalyzeWithZoom | GenerateReportsOnly | Inventory | RetentionReports | TriagePreview
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Scope
The Scope parameter specifies the items to include when the action is Export. Valid values are:

- IndexedItemsOnly

- UnindexedItemsOnly

- BothIndexedAndUnindexedItems

This parameter is only meaningful for compliance searches where the IncludeUnindexedItemsEnabled parameter is set to $true.

```yaml
Type: Unknown | IndexedItemsOnly | UnindexedItemsOnly | BothIndexedAndUnindexedItems
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScopeDetails
This parameter is reserved for internal Microsoft use.

```yaml
Type: ComplianceScopeDetail[]
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchName
The SearchName parameter specifies the name of the existing compliance search to associate with the compliance search action. You can specify multiple compliance searches separated by commas.

You can find the compliance search by running the command Get-ComplianceSearch | Format-Table -Auto Name,Status.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchNames
The SearchNames parameter specifies the names of the existing compliance searches to associate with the compliance search action. You separate the compliance searche names by commas.

You can find compliance search names by running the command Get-ComplianceSearch | Format-Table -Auto Name,Status.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharePointArchiveFormat
The SharePointArchiveFormat parameter specifies how to export SharePoint search results. Valid values are:

- PerUserPst: One PST file for each user. This is the default value.

- SinglePst: One PST file that contains all exported files.

- SingleFolderPst: One PST file with a single root folder for the entire export.

- IndividualMessage: Export each file to a message using the .msg format.

- SingleZip: One ZIP file that contains all exported files.

- PerUserZip: One ZIP file for each user.

```yaml
Type: Unknown | SinglePst | PerUserPst | IndividualMessage | SingleZip | PerUserZip | SingleFolderPst
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShareRootPath
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: Set3
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
This parameter is reserved for internal Microsoft use.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
This parameter doesn't work in the Office 365 Security & Compliance Center.

The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Exchange Server 2016, Office 365 Security & Compliance Center
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

###  
To see the input types that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?linkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

###  
To see the return types, which are also known as output types, that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?linkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS

[Online Version](https://technet.microsoft.com/library/a3a2897c-07a8-41d6-99cd-f2440613fbce.aspx)

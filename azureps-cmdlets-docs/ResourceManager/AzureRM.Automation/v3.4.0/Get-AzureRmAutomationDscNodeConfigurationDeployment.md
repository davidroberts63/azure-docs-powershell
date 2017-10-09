---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
ms.assetid: 32CF9BF7-519F-4B5D-9F2B-3CC556A77A48
online version:
schema: 2.0.0
content_git_url: https://github.com/Visual-Studio-China/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationDscNodeConfigurationDeployment.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Get-AzureRmAutomationDscNodeConfigurationDeployment.md
---

# Get-AzureRmAutomationDscNodeConfigurationDeployment

## SYNOPSIS
Gets DSC Node configuration deployments in Automation.

## SYNTAX

### ByAll (Default)
```
Get-AzureRmAutomationDscNodeConfigurationDeployment [[-Status] <String>] [[-StartTime] <DateTimeOffset>]
 [[-EndTime] <DateTimeOffset>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByJobId
```
Get-AzureRmAutomationDscNodeConfigurationDeployment -JobId <Guid> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzureRmAutomationDscNodeConfigurationDeployment** cmdlet deployes an APS Desired State Configuration (DSC) node configuration in Azure Automation.

## EXAMPLES

### Example 1: Get a node configuration deployment
```
PS C:\> $deployment = Get-AzureRmAutomationDscNodeConfigurationDeployment -JobId 6248f59e-e2fa-498c-a4c0-4ce33b8bc0b5 `
            -AutomationAccountName "Contoso01"  `
            -ResourceGroupName "ResourceGroup01" `
            
ResourceGroupName     : ResourceGroup01
AutomationAccountName : Contoso01
JobId                 : 6248f59e-e2fa-498c-a4c0-4ce33b8bc0b5
Job                   : Microsoft.Azure.Commands.Automation.Model.Job
JobStatus             : Running
nodeStatus            : {System.Collections.Generic.Dictionary`2[System.String,System.String],
                        System.Collections.Generic.Dictionary`2[System.String,System.String]}

PS C:\> $ns = $deployment | select nodeStatus
PS C:\> $ns.nodeStatus

Key        Value
---        -----
WebServer  Pending
WebServer2 Pending
WebServer3 Compliant
```

The above command deploys the DSC node configuration named "Config01.Node1" to the given two-dimensional array of Node Names. The deployment happens in a staged manner.

## PARAMETERS

### -JobId
Specifies the Job id of an existing deployment job.

```yaml
Type: System.Guid
Parameter Sets: ByJobId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of a resource group in which this cmdlet compiles a configuration.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AutomationAccountName
Specifies the name of the Automation account that contains the DSC configuration that this cmdlet compiles.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Status of the Job filter.

```yaml
Type: System.String
Parameter Sets: ByAll
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Start time filter.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
End time filter.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.NodeConfigurationDeployment

## NOTES

## RELATED LINKS

[Start-AzureRmAutomationDscCompilationJob](./Start-AzureRmAutomationDscCompilationJob.md)

[Import-AzureRmAutomationDscNodeConfiguration](./Import-AzureRmAutomationDscNodeConfiguration.md)

[Start-AzureRmAutomationDscNodeConfigurationDeployment](./Start-AzureRmAutomationDscNodeConfigurationDeployment.md)

[Stop-AzureRmAutomationDscNodeConfigurationDeployment](./Stop-AzureRmAutomationDscNodeConfigurationDeployment.md)

[Get-AzureRmAutomationDscNodeConfigurationDeploymentSchedule](./Get-AzureRmAutomationDscNodeConfigurationDeploymentSchedule.md)

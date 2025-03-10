---
title: "PowerShell: Configure active geo-replication for Azure SQL Database"
description: Use an Azure PowerShell example script to set up active geo-replication for Azure SQL Database and fail it over.
author: AbdullahMSFT
ms.author: amamun
ms.reviewer: wiassaf, mathoma
ms.date: 03/12/2019
ms.service: sql-database
ms.subservice: high-availability
ms.topic: sample
ms.custom:
  - "sqldbrb=1"
  - "devx-track-azurepowershell"
ms.devlang: PowerShell
---

# Use PowerShell to configure active geo-replication for a database in Azure SQL Database

[!INCLUDE[appliesto-sqldb](../../includes/appliesto-sqldb.md)]

This Azure PowerShell script example configures active geo-replication for a database in Azure SQL Database and fails it over to a secondary replica of the database.

[!INCLUDE [quickstarts-free-trial-note](../../includes/quickstarts-free-trial-note.md)]
[!INCLUDE [updated-for-az](../../includes/updated-for-az.md)]
[!INCLUDE [cloud-shell-try-it.md](../../includes/cloud-shell-try-it.md)]

If you choose to install and use PowerShell locally, this tutorial requires Az PowerShell 1.4.0 or later. If you need to upgrade, see [Install Azure PowerShell module](/powershell/azure/install-az-ps). If you are running PowerShell locally, you also need to run `Connect-AzAccount` to create a connection with Azure.

## Sample scripts

[!code-powershell-interactive[main](~/../powershell_scripts/sql-database/setup-geodr-and-failover/setup-geodr-and-failover-single-database.ps1?highlight=18-21 "Set up active geo-replication for single database")]

## Clean up deployment

Use the following command to remove  the resource group and all resources associated with it.

```powershell
Remove-AzResourceGroup -ResourceGroupName $primaryresourcegroupname
Remove-AzResourceGroup -ResourceGroupName $secondaryresourcegroupname
```

## Script explanation

This script uses the following commands. Each command in the table links to command-specific documentation.

| Command | Notes |
|---|---|
| [New-AzResourceGroup](/powershell/module/az.resources/new-azresourcegroup) | Creates a resource group in which all resources are stored. |
| [New-AzSqlServer](/powershell/module/az.sql/new-azsqlserver) | Creates a server that hosts databases and elastic pools. |
| [New-AzSqlElasticPool](/powershell/module/az.sql/new-azsqlelasticpool) | Creates an elastic pool. |
| [Set-AzSqlDatabase](/powershell/module/az.sql/set-azsqldatabase) | Updates database properties or moves a database into, out of, or between elastic pools. |
| [New-AzSqlDatabaseSecondary](/powershell/module/az.sql/new-azsqldatabasesecondary)| Creates a secondary database for an existing database and starts data replication. |
| [Get-AzSqlDatabase](/powershell/module/az.sql/get-azsqldatabase)| Gets one or more databases. |
| [Set-AzSqlDatabaseSecondary](/powershell/module/az.sql/set-azsqldatabasesecondary)| Switches a secondary database to be primary to initiate failover.|
| [Get-AzSqlDatabaseReplicationLink](/powershell/module/az.sql/get-azsqldatabasereplicationlink) | Gets the geo-replication links between an Azure SQL Database and a resource group or logical SQL server. |
| [Remove-AzSqlDatabaseSecondary](/powershell/module/az.sql/remove-azsqldatabasesecondary) | Terminates data replication between a database and the specified secondary database. |
| [Remove-AzResourceGroup](/powershell/module/az.resources/remove-azresourcegroup) | Deletes a resource group including all nested resources. |


## Next steps

For more information on Azure PowerShell, see [Azure PowerShell documentation](/powershell/azure/).

Additional SQL Database PowerShell script samples can be found in the [Azure SQL Database PowerShell scripts](../powershell-script-content-guide.md).

---
description: "Create rowset with ICommand::Execute (Native Client OLE DB provider)"
title: "Create rowset with ICommand::Execute (Native Client OLE DB provider) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: native-client
ms.topic: "reference"
helpviewer_keywords: 
  - "rowsets [OLE DB], creating"
  - "SQL Server Native Client OLE DB provider, rowsets"
  - "OLE DB rowsets, creating"
  - "Execute method"
ms.assetid: 9b530b7d-8165-49d4-a978-5ced17c6705e
author: markingmyname
ms.author: maghan
monikerRange: ">=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# Creating Rowsets with ICommand::Execute in SQL Server Native Client
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  For rowsets created by using the **ICommand::Execute** method, the properties that you want in the resulting rowset can constrain the text of the command. This is especially critical for consumers that support dynamic command text.  
  
 The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cannot use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors to support the multiple-rowset results generated by many commands. If a consumer requests a rowset requiring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursor support, an error occurs if the command text generates more than a single rowset as its result. For more information, see [Commands Generating Multiple-Rowset Results](../../relational-databases/native-client-ole-db-commands/commands-generating-multiple-rowset-results.md).  
  
 Scrollable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider rowsets are supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imposes limitations on cursors that are sensitive to changes made by other users of the database. Specifically, the rows in some cursors cannot be ordered, and trying to create a rowset by using a command that contains an SQL ORDER BY clause can fail. For more information, see [Rowsets and SQL Server Cursors](../../relational-databases/native-client-ole-db-rowsets/rowsets-and-sql-server-cursors.md).  
  
## See Also  
 [Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md)  
  
  

---
description: Хранимые процедуры OLE-автоматизации (Transact-SQL)
title: Хранимые процедуры OLE Automation (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- system stored procedures [SQL Server], OLE Automation
- OLE Automation [SQL Server], stored procedures
ms.assetid: ff16a833-01fe-4877-8aa6-55b72603ec2e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 820a100a4da0ed62fd22bb64b22bf83daacee490
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88454767"
---
# <a name="ole-automation-stored-procedures-transact-sql"></a>Хранимые процедуры OLE-автоматизации (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает следующие системные хранимые процедуры, которые позволяют использовать объекты OLE-автоматизации внутри пакета языка [!INCLUDE[tsql](../../includes/tsql-md.md)]. По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] блокирует доступ к хранимым процедурам OLE-автоматизации, поскольку этот компонент отключается как часть конфигурации безопасности для данного сервера. Системный администратор может включить доступ к хранимым процедурам OLE-автоматизации с помощью процедуры sp_configure. Дополнительные сведения см. в разделе [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).  

:::row:::
    :::column:::
        [sp_OACreate](../../relational-databases/system-stored-procedures/sp-oacreate-transact-sql.md)

        [sp_OADestroy](../../relational-databases/system-stored-procedures/sp-oadestroy-transact-sql.md)

        [sp_OAGetErrorInfo](../../relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql.md)

        [sp_OAGetProperty, хранимая процедура](../../relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql.md)
    :::column-end:::
    :::column:::
        [sp_OAMethod](../../relational-databases/system-stored-procedures/sp-oamethod-transact-sql.md)

        [sp_OASetProperty](../../relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql.md)

        [sp_OAStop](../../relational-databases/system-stored-procedures/sp-oastop-transact-sql.md)

        [Синтаксис иерархии объектов (Transact-SQL)](../../relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql.md)
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также:  
 [Системные хранимые процедуры &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Параметр конфигурации сервера «Ole Automation Procedures»](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  

---
description: dbo.sysoperators (Transact-SQL)
title: Операторы dbo.sys(Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysoperators
- dbo.sysoperators
- dbo.sysoperators_TSQL
- sysoperators_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysoperators system table
ms.assetid: c2afa20c-b15f-46ca-ae74-2eb65909409e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3a16b2af8e9752b0df51a1cc60a227e0b055b798
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88446637"
---
# <a name="dbosysoperators-transact-sql"></a>dbo.sysoperators (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит по одной строке для каждого оператора агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**идентификатор**|**int**|Идентификатор оператора.|  
|**name**|**sysname**|Имя оператора.|  
|**доступной**|**tinyint**|Состояние рассылки уведомлений по предупреждениям (логическое значение). Если значение равно **1**, этот оператор может получать уведомления при возникновении предупреждения.|  
|**email_address**|**nvarchar (100)**|Адрес электронной почты оператора.|  
|**last_email_date**|**int**|Дата последнего получения оператором уведомления о предупреждении по электронной почте.|  
|**last_email_time**|**int**|Время последнего получения оператором уведомления о предупреждении по электронной почте.|  
|**pager_address**|**nvarchar (100)**|Адрес пейджера для данного оператора.|  
|**last_pager_date**|**int**|Дата последнего получения оператором уведомления о предупреждении на пейджер.|  
|**last_pager_time**|**int**|Время последнего получения оператором уведомления о предупреждении на пейджер.|  
|**weekday_pager_start_time**|**int**|Время (с понедельника по пятницу), после которого данный оператор может получать уведомления о предупреждении, отправляемые на пейджер.|  
|**weekday_pager_end_time**|**int**|Время (с понедельника по пятницу), после которого данный оператор не может получать уведомления о предупреждении, отправляемые на пейджер.|  
|**saturday_pager_start_time**|**int**|Время (в субботу), после которого данный оператор может получать уведомления о предупреждении, отправляемые на пейджер.|  
|**saturday_pager_end_time**|**int**|Время (в субботу), после которого данный оператор не может получать уведомления о предупреждении, отправляемые на пейджер.|  
|**sunday_pager_start_time**|**int**|Время (в воскресенье), после которого данный оператор может получать уведомления о предупреждениях, отправленные на пейджер.|  
|**sunday_pager_end_time**|**int**|Время (в воскресенье), после которого данный оператор не может получать уведомления о предупреждении, отправленные на пейджер.|  
|**pager_days**|**tinyint**|Битовая маска, определяющая дни недели, во время которых оператор может получать уведомления о предупреждении, отправленные на пейджер.|  
|**netsend_address**|**nvarchar (100)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**last_netsend_date**|**int**|Дата отправки последнего сетевого сообщения оператору с указанным идентификатором.|  
|**last_netsend_time**|**int**|Время отправки последнего сетевого сообщения оператору с указанным идентификатором.|  
|**category_id**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
  
## <a name="see-also"></a>См. также  
 [Агент SQL Serverные таблицы &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/sql-server-agent-tables-transact-sql.md)  
  
  

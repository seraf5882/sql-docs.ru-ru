---
description: dbo.sysjobstepslogs (Transact-SQL)
title: dbo.sysжобстепслогс (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.sysjobstepslogs_TSQL
- sysjobstepslogs_TSQL
- sysjobstepslogs
- dbo.sysjobstepslogs
dev_langs:
- TSQL
helpviewer_keywords:
- sysjobstepslogs system table
ms.assetid: 128c25db-0b71-449d-bfb2-38b8abcf24a0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f32042c01db8a35f9ce44fe938b19e4ae8e6118b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88373831"
---
# <a name="dbosysjobstepslogs-transact-sql"></a>dbo.sysjobstepslogs (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Содержит журнал шагов задания для всех шагов задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которые настроены для записи выхода шага задания в таблицу. Эта таблица хранится в базе данных **msdb** .  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**log_id**|**int**|Идентификатор журнала шагов задания.|  
|**Журналь**|**nvarchar(max)**|Содержимое журнала шагов задания.|  
|**date_created**|**datetime**|Дата и время создания журнала шагов задания.|  
|**date_modified**|**datetime**|Дата и время последнего изменения журнала шагов задания.|  
|**log_size**|**int**|Размер журнала шагов задания в байтах.|  
|**step_uid**|**uniqueidentifier**|Уникальный идентификатор шага задания.|  
  
## <a name="see-also"></a>См. также:  
 [sp_help_jobsteplog &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-jobsteplog-transact-sql.md)   
 [sp_delete_jobsteplog &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-jobsteplog-transact-sql.md)  
  
  

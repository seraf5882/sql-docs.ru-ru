---
description: sys.server_event_session_targets (Transact-SQL)
title: sys. server_event_session_targets (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_event_session_targets_TSQL
- sys.server_event_session_targets_TSQL
- sys.server_event_session_targets
- server_event_session_targets
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_event_session_targets catalog view
- xe
ms.assetid: dda4879d-57ae-4267-b410-1ef5c37404c7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0d7a67610844722fc7b280223e31f096ad534679
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88475308"
---
# <a name="sysserver_event_session_targets-transact-sql"></a>sys.server_event_session_targets (Transact-SQL)
[!INCLUDE[sqlserver](../../includes/applies-to-version/sqlserver.md)]

  Возвращает строку для каждой цели события для сеанса событий.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|Идентификатор сеанса событий. Не допускает значение NULL.|  
|target_id|**int**|Идентификатор цели. Идентификатор уникален внутри объекта сеанса событий. Не допускает значение NULL.|  
|name|**sysname**|Имя цели события. Не допускает значение NULL.|  
|пакет|**sysname**|Имя пакета событий, который содержит цель события. Не допускает значение NULL.|  
|module|**sysname**|Имя модуля, который содержит цель события. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 необходимо разрешение VIEW SERVER STATE на сервере.  
  
## <a name="remarks"></a>Remarks  
 Это представление имеет следующее количество элементов связей.  
  
| От | Кому | Связь |
| ---- | -- | ------------ |
|sys.server_event_session_targets.event_session_id|sys. server_event_sessions. event_session_id|Многие к одному|  
  
## <a name="see-also"></a>См. также:  
 [Представления каталога (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Представления каталога расширенных событий &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [Расширенные события](../../relational-databases/extended-events/extended-events.md)  
  
  

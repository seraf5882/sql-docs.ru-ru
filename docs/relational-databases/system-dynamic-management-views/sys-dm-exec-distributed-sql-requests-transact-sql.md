---
description: sys. dm_exec_distributed_sql_requests (Transact-SQL)
title: sys. dm_exec_distributed_sql_requests (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- DM_EXEC_DISTRIBUTED_SQL_REQUESTS_TSQL
- SYS.DM_EXEC_DISTRIBUTED_SQL_REQUESTS_TSQL
- DM_EXEC_DISTRIBUTED_SQL_REQUESTS
dev_langs:
- TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- sys.dm_exec_distributed_requests management view
- dm_exec_distributed_requests management view
ms.assetid: d065dc01-35d4-472f-9554-53ac41e7d104
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: fdda8279e49c5e1884cbd539e1a3158431e53b41
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88398850"
---
# <a name="sysdm_exec_distributed_sql_requests-transact-sql"></a>sys. dm_exec_distributed_sql_requests (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  Содержит сведения обо всех распределениях SQL-запросов в рамках шага SQL в запросе.  В этом представлении отображаются данные за последние 1000 запросов. Активные запросы всегда имеют данные, представленные в этом представлении.  
  
|Имя столбца|Тип данных|Description|Диапазон|  
|-----------------|---------------|-----------------|-----------|  
|execution_id|**nvarchar(32)**|execution_id и step_index сделать ключ для этого представления. Уникальный числовой идентификатор, связанный с запросом.|См. раздел ID в [sys. dm_exec_requests &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)|  
|step_index|**int**|Индекс шага запроса, частью которого является это распространение.|См. раздел step_index в [sys. dm_exec_distributed_request_steps &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-distributed-request-steps-transact-sql.md).|  
|compute_node_id|**int**|Тип операции, представленной этим шагом.|См. раздел compute_node_id в [sys. dm_exec_compute_nodes &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-nodes-transact-sql.md).|  
|distribution_id|**int**|Место исполнения шага.|Задайте значение-1 для запросов, выполняемых в области узла, а не в области распространения.|  
|status|**nvarchar(32)**|Состояние этого шага|Активный, отмененный, завершенный, сбой, поставлен в очередь|  
|error_id|**nvarchar (36)**|Уникальный идентификатор ошибки, связанной с этим шагом, если таковой имеется|Ознакомьтесь с идентификатором [sys. dm_exec_compute_node_errors &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-node-errors-transact-sql.md), значение null, если ошибка не возникла.|  
|start_time|**datetime**|Время начала выполнения этапа|Меньше или равно текущему времени и больше или равно end_compile_time запроса, к которому относится этот шаг.|  
|end_time|**datetime**|Время, когда выполнение этого шага было завершено, было отменено или завершилось сбоем.|Меньшее или равное текущему времени и больше или равно start_time, установите значение NULL для шагов, выполняемых в данный момент или в очереди.|  
|total_elapsed_time|**int**|Общее количество времени выполнения шага запроса (в миллисекундах)|Между 0 и разностью между end_time и start_time. 0 для шагов в очереди.|  
|row_count|**bigint**|Общее число строк, измененных или возвращенных этим запросом|0 для шагов, которые не изменяют или возвращают данные, количество затронутых строк в противном случае. Задайте значение-1 для шагов DMS.|  
|spid|**int**|Идентификатор сеанса на SQL Server экземпляре, который исполняет распределение запроса||  
|.|nvarchar(4000)|Содержит полный текст команды этого шага.|Любая допустимая строка запроса для шага. Усекается, если длиннее 4000 символов.|  
  
## <a name="see-also"></a>См. также:  
 [Устранение неполадок в Polybase с помощью динамических административных представлений](https://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [Динамические административные представления и функции (Transact-SQL)](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Динамические административные представления, связанные с базами данных &#40;&#41;Transact-SQL ](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  

---
description: syscollector_execution_stats (Transact-SQL)
title: syscollector_execution_stats (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syscollector_execution_stats
- syscollector_execution_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syscollector_execution_stats view
- data collector view
ms.assetid: 23e35ac5-fbbf-4922-970c-f4fac44c1263
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed50c37df682bf3ea41478c29847ca7daba0e448
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88490072"
---
# <a name="syscollector_execution_stats-transact-sql"></a>syscollector_execution_stats (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Отображает сведения о ходе выполнения задачи для набора элементов сбора или пакета.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**log_id**|**bigint**|Определяет выполнение каждого набора элементов сбора. Используется для соединения этого представления с другими подробными журналами. Не допускает значение NULL.|  
|**task_name**|**nvarchar(128)**|Имя набора сбора или задачи пакета, для которого производится отображение текущей информации. Не допускает значение NULL.|  
|**execution_row_count_in**|**int**|Количество обработанных строк на момент запуска потока данных. Допускает значение NULL.|  
|**execution_row_count_out**|**int**|Количество обработанных строк на момент окончания потока данных. Допускает значение NULL.|  
|**execution_row_count_errors**|**int**|Количество строк с ошибками, обработанных в потоке данных. Допускает значение NULL.|  
|**execution_time_ms**|**int**|Время, требуемое для завершения задачи, в миллисекундах. Допускает значение NULL.|  
|**log_time**|**datetime**|Время занесения данной информации в журнал. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 Требуется разрешение SELECT для **dc_operator**.  
  
## <a name="see-also"></a>См. также:  
 [Хранимые процедуры сборщика данных (Transact-SQL)](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Представления сборщика данных &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [Сбор данных](../../relational-databases/data-collection/data-collection.md)  
  
  

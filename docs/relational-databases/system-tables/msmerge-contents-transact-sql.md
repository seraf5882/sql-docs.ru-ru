---
description: MSmerge_contents (Transact-SQL)
title: MSmerge_contents (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSmerge_contents
- MSmerge_contents_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_contents system table
ms.assetid: 8d68a61a-683f-4b20-92f9-c0a8d9ba0ad1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 81320e7cc5301577369d6d3d89cbfb53f77b0e6e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88469114"
---
# <a name="msmerge_contents-transact-sql"></a>MSmerge_contents (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Таблица **MSmerge_contents** содержит по одной строке для каждой строки, измененной в текущей базе данных с момента ее публикации. Данная таблица используется процессом слияния для определения изменившихся строк. Эта таблица хранится в базах данных публикации и подписки.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**tablenick**|**int**|Псевдоним опубликованной таблицы.|  
|**уникаль**|**uniqueidentifier**|Идентификатор данной строки.|  
|**поколения**|**bigint**|Создание строки, определяемой **табленикк** и **rowguid**.|  
|**partchangegen**|**bigint**|Поколение, связанное с последним изменением данных, при котором могла измениться принадлежность строки к публикации с фильтром.|  
|**журнала преобразований**|**varbinary (501)**|Пары псевдонимов подписчиков и номеров версий, используемые для ведения журнала изменений данной строки.|  
|**colvl**|**varbinary (7489)**|Сведения о версии столбца.|  
|**marker**|**uniqueidentifier**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**logical_record_parent_rowguid**|**uniqueidentifier**|Определяет родительскую строку верхнего уровня в **MSmerge_contents** (по **rowguid**) для каждой соответствующей дочерней строки в логической записи.|  
|**logical_record_lineage**|**varbinary (501)**|Пары псевдонимов подписчиков и номеров версий, используемые для ведения журнала изменений родительской строки верхнего уровня в логической записи. Для всех дочерних строк в логической записи это значение равно NULL.|  
|**logical_relation_change_gen**|**bigint**|Поколение, связанное с последним изменением, вызвавшим перегруппировку в логической записи, при которой существующая строка была внесена в логическую запись или исключена оттуда.|  
  
## <a name="see-also"></a>См. также  
 [Таблицы репликации &#40;&#41;Transact-SQL ](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Представления репликации (Transact-SQL)](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  

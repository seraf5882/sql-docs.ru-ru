---
title: sys. FileTable (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- filetables
- filetables_TSQL
- sys.filetables
- sys.filetables_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.filetables catalog view
ms.assetid: a740be59-cd52-4707-9ad2-5203669a63ac
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d83b58f8ff153583775e2e321c5524b43b205745
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85738771"
---
# <a name="sysfiletables-transact-sql"></a>sys.filetables (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Возвращает по одной строке для каждой таблицы FileTable в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Дополнительные сведения о таблицах FileTable см. в разделе [Таблицы FileTable (SQL Server)](../../relational-databases/blob/filetables-sql-server.md).    
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**object_id**||Идентификационный номер объекта. Уникален в базе данных.<br /><br /> Дополнительные сведения см [. в таблице sys. objects &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**is_enabled**|**bit**|1 = Таблица FileTable находится во включенном состоянии.|  
|**directory_name**|**varchar (255)**|Имя корневого каталога для таблицы FileTable.|  
|**filename_collation_id**||Является идентификатором параметров сортировки, определенных для таблицы FileTable|  
|**filename_collation_name**||Является именем параметров сортировки, определенных для таблицы FileTable|  
  
## <a name="see-also"></a>См. также  
 [Управление таблицами FileTable](../../relational-databases/blob/manage-filetables.md)   
 [FileTables (SQL Server)](../../relational-databases/blob/filetables-sql-server.md)  
  
  

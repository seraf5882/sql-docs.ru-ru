---
description: sys. masked_columns (Transact-SQL)
title: sys. masked_columns (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 02/25/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.masked_columns
- masked_columns_tsql
- sys.masked_columns_tsql
- masked_columns
helpviewer_keywords:
- sys.masked_columns catalog view
ms.assetid: 671577e4-d757-4b8d-9aa9-0fc8d51ea9ca
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 28946de442b72309f3284338e6f426c655a4d0f8
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "88455267"
---
# <a name="sysmasked_columns-transact-sql"></a>sys. masked_columns (Transact-SQL)
[!INCLUDE [sqlserver2016-asdb-asdbmi-asa](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi-asa.md)]

  Используйте представление **sys. masked_columns** для запроса столбцов таблицы, к которым применена функция динамического маскирования данных. Это представление наследуется из представления **sys.columns** . Оно возвращает все столбцы в представлении **sys.columns** , а также столбцы **is_masked** и **masking_function** , указывающие, маскирован ли столбец, и если да, то какая функция маскирования определена. В этом представлении отображаются только столбцы, к которым применена функция маскирования.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|object_id|**int**|Идентификатор объекта, которому принадлежит этот столбец.|  
|name|**sysname**|Имя столбца. Уникален в пределах объекта.|  
|column_id|**int**|Идентификатор столбца. Уникален в пределах объекта.<br /><br /> Идентификаторы столбца могут быть непоследовательными.|  
|**sys. masked_columns** возвращает много столбцов, наследуемых от **sys. Columns**.|Различная|Дополнительные определения столбцов см. в разделе [sys. columns &#40;&#41;Transact-SQL ](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md) .|  
|is_masked|**bit**|Указывает, является ли столбец маскированным. 1 означает маскирование.|  
|masking_function|**nvarchar(4000)**|Функция маскирования для столбца.|  
  
## <a name="remarks"></a>Комментарии  
  
## <a name="permissions"></a>Разрешения  
 Это представление возвращает сведения о таблицах, в которых пользователь имеет определенное разрешение для таблицы или пользователь имеет разрешение VIEW ANY DEFINITION.  
  
## <a name="example"></a>Пример  
 Следующий запрос соединяет **sys. masked_columns** с **sys. Tables** , чтобы получить сведения обо всех маскированных столбцах.  
  
```  
SELECT tbl.name as table_name, c.name AS column_name, c.is_masked, c.masking_function  
FROM sys.masked_columns AS c  
JOIN sys.tables AS tbl   
    ON c.object_id = tbl.object_id  
WHERE is_masked = 1;  
```  
  
## <a name="see-also"></a>См. также  
 [динамическое маскирование данных](../../relational-databases/security/dynamic-data-masking.md)   
 [sys.columns (Transact-SQL)](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md)  
  
  
